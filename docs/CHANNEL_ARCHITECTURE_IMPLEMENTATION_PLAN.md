---
title: CHANNEL_ARCHITECTURE_IMPLEMENTATION_PLAN.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 2.0.2
date_created: 2025-11-17
last_modified: 2025-11-17
status: draft
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, IMPLEMENTATION, CHANNELS, ARCHITECTURE]
collections: [WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER]
in_this_file_we_have: [OVERVIEW, REQUIREMENTS, EXISTING_CODE, IMPLEMENTATION_PHASES, DATABASE_CHANGES, CODE_CHANGES, TESTING, INTEGRATION]
superpositionally: ["FILEID_CHANNEL_ARCHITECTURE_PLAN"]
shadow_aliases: []
parallel_paths: []
---

# Channel Architecture Implementation Plan

**Date**: 2025-11-17  
**Version**: LUPOPEDIA_PLATFORM v0.0.8 → v1.0.0  
**Status**: Implementation Plan  
**Priority**: High (Core Feature)

---

## OVERVIEW

Implement full channel architecture supporting **000-999 channels (maximum 999)** with direct mapping: **Agent ID = Channel Number**. This enables the multi-agent broadcasting system and agent creation workflow.

**Key Requirements**:
- Channels: 000-999 (maximum 999)
- Direct mapping: Agent ID = Channel Number
- Multi-participant conversations (not one-on-one)
- Multi-agent broadcasting (multiple agents on same channel)
- Integration with WOLFIE Headers v2.0.2
- Radio network model

---

## REQUIREMENTS

### Core Requirements

1. **Channel Range**: 000-999 (maximum 999)
   - Zero-padded 3-digit format (e.g., "000", "001", "010", "999")
   - Validation: Must be between 0 and 999 (inclusive)
   - Hard limit: Cannot exceed 999

2. **Direct Mapping**: Agent ID = Channel Number
   - Agent ID 008 → Channel 008
   - Agent ID 010 → Channel 010
   - Agent ID 999 → Channel 999
   - No lookup tables (brittleness is a feature)

3. **Multi-Participant Conversations**
   - Multiple agents can be on same channel
   - Multiple users can be on same channel
   - Overlapping chatter (multi-voice chorus)
   - Not one-on-one sessions

4. **Multi-Agent Broadcasting**
   - Multiple agents broadcast simultaneously
   - Multiple agents listen simultaneously
   - Radio network model

5. **WOLFIE Headers v2.0.2 Integration**
   - Use `channel_number` from YAML frontmatter
   - Use `agent_id` for direct mapping
   - Support `agent_name` from database

---

## EXISTING_CODE

### Current Implementation

**Files Found**:
- ✅ `public/classes/Channel.php` - Channel domain model
- ✅ `public/classes/controllers/ChannelController.php` - Channel controller
- ✅ `public/classes/controllers/PageController.php` - Has channel methods
- ✅ Session-based channel management (`$_SESSION['onchannel']`)
- ✅ Database tables: `channels`, `chat_channels`, `user_channels`

**Current Capabilities**:
- Channel loading by ID/name
- Channel creation/update
- Session-based channel switching
- Participant management
- Message retrieval
- Channel statistics

**Current Limitations**:
- Channel range not explicitly limited to 000-999
- No direct Agent ID = Channel Number mapping
- No multi-agent broadcasting system
- No integration with WOLFIE Headers v2.0.2 agent system

---

## IMPLEMENTATION_PHASES

### Phase 1: Database & Validation (Foundation)

**Tasks**:
1. **Validate Channel Range in Database**
   - Add CHECK constraint: `channel_id BETWEEN 0 AND 999`
   - Update `channels` table to support 000-999
   - Add validation in Channel.php class

2. **Add Agent ID Column to Channels Table**
   - Add `agent_id` BIGINT(20) UNSIGNED column
   - Add index on `agent_id`
   - Populate from existing channel data if needed

3. **Update Channel Validation**
   - Validate channel ID range (000-999)
   - Validate zero-padding format
   - Enforce maximum 999 limit

**Files to Modify**:
- `database/migrations/1075_validate_channel_range_000_999.sql` (NEW)
- `database/migrations/1076_add_agent_id_to_channels.sql` (NEW)
- `public/classes/Channel.php` - Add validation methods

---

### Phase 2: Agent ID = Channel Number Mapping

**Tasks**:
1. **Implement Direct Mapping Logic**
   - When agent created, assign channel = agent_id
   - When channel accessed, validate agent_id matches
   - No lookup tables (direct mapping)

2. **Update Channel Creation**
   - Auto-assign channel number from agent_id
   - Validate agent_id is in range 000-999
   - Create channel automatically when agent created

3. **Update Channel Loading**
   - Load channel by agent_id (direct mapping)
   - Load channel by channel_id (000-999)
   - Support both methods

**Files to Modify**:
- `public/classes/Channel.php` - Add agent mapping methods
- `public/classes/controllers/ChannelController.php` - Update routing
- `public/classes/Agent.php` (if exists) - Auto-create channel

---

### Phase 3: Multi-Participant Support

**Tasks**:
1. **Update Participant Management**
   - Allow multiple agents on same channel
   - Allow multiple users on same channel
   - Track agent participants separately from user participants

2. **Update Message System**
   - Support messages from multiple agents
   - Support messages from multiple users
   - Tag messages with agent_id or user_id

3. **Update Channel Statistics**
   - Count agent participants separately
   - Count user participants separately
   - Total participant count = agents + users

**Files to Modify**:
- `public/classes/Channel.php` - Update participant methods
- Database: Add `agent_participants` table or extend `user_channels`

---

### Phase 4: Multi-Agent Broadcasting

**Tasks**:
1. **Implement Broadcasting System**
   - Allow multiple agents to broadcast simultaneously
   - Allow multiple agents to listen simultaneously
   - Queue broadcasts if needed

2. **Implement Message Routing**
   - Route messages to all agents on channel
   - Route messages to all users on channel
   - Support overlapping chatter

3. **Implement Radio Network Model**
   - Channel = frequency band
   - Multiple agents = multiple radios on same frequency
   - Overlapping chatter = multi-voice chorus

**Files to Create/Modify**:
- `public/classes/AgentBroadcast.php` (NEW) - Broadcasting system
- `public/classes/Channel.php` - Add broadcasting methods
- `public/api/channels.php` - Add broadcast endpoints

---

### Phase 5: WOLFIE Headers v2.0.2 Integration

**Tasks**:
1. **Integrate with WOLFIE Headers**
   - Read `channel_number` from YAML frontmatter
   - Read `agent_id` from YAML frontmatter
   - Use `agent_name` from database

2. **Update Channel Resolution**
   - Resolve channel from WOLFIE Headers
   - Validate channel_number matches agent_id
   - Support channel fallback chain

3. **Update Agent File Naming**
   - Use `who_is_agent_[channel_id]_[agent_name].php` convention
   - Validate file naming matches channel_id
   - Auto-create agent files when channels created

**Files to Modify**:
- `public/classes/Channel.php` - Add WOLFIE Headers integration
- `public/classes/WOLFIEHeaders.php` (if exists) - Add channel resolution

---

## DATABASE_CHANGES

### Migration 1075: Validate Channel Range

```sql
-- Migration 1075: Validate channel range (000-999, maximum 999)
-- Date: 2025-11-17

-- Add CHECK constraint to channels table
ALTER TABLE `channels`
ADD CONSTRAINT `chk_channel_id_range` 
CHECK (`id` >= 0 AND `id` <= 999);

-- Add CHECK constraint to chat_channels table
ALTER TABLE `chat_channels`
ADD CONSTRAINT `chk_chat_channel_id_range` 
CHECK (`channel_id` >= 0 AND `channel_id` <= 999);

-- Add CHECK constraint to user_channels table
ALTER TABLE `user_channels`
ADD CONSTRAINT `chk_user_channel_id_range` 
CHECK (`channel_id` >= 0 AND `channel_id` <= 999);

-- Add CHECK constraint to context_channels table
ALTER TABLE `context_channels`
ADD CONSTRAINT `chk_context_channel_id_range` 
CHECK (`channel_id` >= 0 AND `channel_id` <= 999);
```

### Migration 1076: Add Agent ID to Channels

```sql
-- Migration 1076: Add agent_id to channels table
-- Date: 2025-11-17

-- Add agent_id column
ALTER TABLE `channels`
ADD COLUMN `agent_id` BIGINT(20) UNSIGNED NULL DEFAULT NULL
COMMENT 'Agent ID (direct mapping: agent_id = channel_id, 000-999)'
AFTER `id`;

-- Add index
CREATE INDEX `idx_agent_id` ON `channels` (`agent_id`);

-- Add CHECK constraint for agent_id range
ALTER TABLE `channels`
ADD CONSTRAINT `chk_agent_id_range` 
CHECK (`agent_id` IS NULL OR (`agent_id` >= 0 AND `agent_id` <= 999));

-- Populate agent_id from id where applicable (for existing agent channels)
UPDATE `channels` 
SET `agent_id` = `id` 
WHERE `id` BETWEEN 0 AND 999 
AND `channel_type` IN ('ai_chat', 'group');
```

---

## CODE_CHANGES

### 1. Update Channel.php Class

**Add Methods**:
```php
/**
 * Validate channel ID range (000-999, maximum 999)
 * @param int $channelId Channel ID
 * @return bool Is valid
 */
public function isValidChannelId($channelId) {
    return ($channelId >= 0 && $channelId <= 999);
}

/**
 * Get channel by agent ID (direct mapping)
 * @param int $agentId Agent ID (000-999)
 * @return bool Success
 */
public function loadByAgentId($agentId) {
    if (!$this->isValidChannelId($agentId)) {
        return false;
    }
    // Direct mapping: agent_id = channel_id
    return $this->loadById($agentId);
}

/**
 * Create channel for agent (auto-assign channel = agent_id)
 * @param int $agentId Agent ID (000-999)
 * @param array $channelData Additional channel data
 * @return bool Success
 */
public function createForAgent($agentId, $channelData = []) {
    if (!$this->isValidChannelId($agentId)) {
        throw new InvalidArgumentException("Agent ID out of range: $agentId (must be 000-999, maximum 999)");
    }
    
    // Direct mapping: channel_id = agent_id
    $channelData['id'] = $agentId;
    $channelData['agent_id'] = $agentId;
    $channelData['channel_name'] = $channelData['channel_name'] ?? "Agent Channel $agentId";
    $channelData['channel_type'] = $channelData['channel_type'] ?? self::TYPE_AI_CHAT;
    
    return $this->create($channelData);
}

/**
 * Get zero-padded channel ID string
 * @return string Zero-padded channel ID (e.g., "008", "010", "999")
 */
public function getZeroPaddedId() {
    if (empty($this->id)) {
        return null;
    }
    return str_pad($this->id, 3, '0', STR_PAD_LEFT);
}
```

**Update Existing Methods**:
- `loadById()` - Add range validation
- `create()` - Add range validation, support agent_id
- `isValidChannelType()` - No changes needed

---

### 2. Update ChannelController.php

**Add Methods**:
```php
/**
 * Get channel by agent ID (direct mapping)
 * @param int $agentId Agent ID (000-999)
 * @return array|null Channel info
 */
public function getChannelByAgentId($agentId) {
    if ($agentId < 0 || $agentId > 999) {
        return null;
    }
    // Direct mapping: agent_id = channel_id
    return $this->getChannelById($agentId);
}

/**
 * Switch to agent's channel (direct mapping)
 * @param int $agentId Agent ID (000-999)
 * @return bool Success
 */
public function switchToAgentChannel($agentId) {
    if ($agentId < 0 || $agentId > 999) {
        return false;
    }
    // Direct mapping: channel_id = agent_id
    return $this->switchChannel($agentId);
}
```

---

### 3. Create AgentBroadcast.php (NEW)

**Purpose**: Handle multi-agent broadcasting on channels

```php
<?php
/**
 * AgentBroadcast - Multi-agent broadcasting system
 * 
 * Handles simultaneous broadcasting and listening for multiple agents on channels
 */
class AgentBroadcast {
    private $db;
    private $channelId;
    
    public function __construct(Database $db, $channelId) {
        $this->db = $db;
        if ($channelId < 0 || $channelId > 999) {
            throw new InvalidArgumentException("Channel ID out of range: $channelId (must be 000-999, maximum 999)");
        }
        $this->channelId = $channelId;
    }
    
    /**
     * Broadcast message from agent to all listeners on channel
     * @param int $agentId Agent ID (000-999)
     * @param string $message Message content
     * @return bool Success
     */
    public function broadcast($agentId, $message) {
        // Validate agent_id range
        if ($agentId < 0 || $agentId > 999) {
            return false;
        }
        
        // Insert message into channel
        // All agents and users on channel will receive it
        // Implementation details...
    }
    
    /**
     * Get all agents listening on channel
     * @return array Agent IDs
     */
    public function getListeningAgents() {
        // Get all agents with agent_id matching channel_id
        // Direct mapping: agent_id = channel_id
        return $this->db->fetchAll(
            "SELECT agent_id FROM agents WHERE agent_id = :channel_id",
            ['channel_id' => $this->channelId]
        );
    }
    
    /**
     * Get all messages on channel (multi-voice chorus)
     * @return array Messages from all agents and users
     */
    public function getChannelMessages() {
        // Get messages from all participants (agents + users)
        // Return in chronological order
        // Implementation details...
    }
}
```

---

## TESTING

### Test Cases

1. **Channel Range Validation**
   - ✅ Test channel 000 (minimum)
   - ✅ Test channel 999 (maximum)
   - ❌ Test channel 1000 (should fail)
   - ❌ Test channel -1 (should fail)

2. **Direct Mapping**
   - ✅ Agent ID 008 → Channel 008
   - ✅ Agent ID 010 → Channel 010
   - ✅ Agent ID 999 → Channel 999
   - ❌ Agent ID 1000 → Should fail

3. **Multi-Participant**
   - ✅ Multiple agents on same channel
   - ✅ Multiple users on same channel
   - ✅ Agents and users together on channel

4. **Multi-Agent Broadcasting**
   - ✅ Multiple agents broadcast simultaneously
   - ✅ All agents receive broadcasts
   - ✅ All users receive broadcasts
   - ✅ Overlapping chatter works

---

## INTEGRATION

### WOLFIE Headers v2.0.2 Integration

1. **Read channel_number from frontmatter**
   ```php
   $channelNumber = $header['channel_number']; // "008"
   $channelId = (int)$channelNumber; // 8
   ```

2. **Read agent_id from frontmatter**
   ```php
   $agentId = (int)$header['agent_id']; // 8
   ```

3. **Validate direct mapping**
   ```php
   if ($agentId !== $channelId) {
       throw new InvalidArgumentException("Agent ID ($agentId) does not match channel number ($channelId)");
   }
   ```

4. **Use agent_name from database**
   ```php
   $agentName = $db->fetchOne(
       "SELECT agent_name FROM content_headers WHERE agent_id = :agent_id LIMIT 1",
       ['agent_id' => $agentId]
   )['agent_name'] ?? null;
   ```

---

## IMPLEMENTATION_CHECKLIST

### Phase 1: Database & Validation
- [ ] Create migration 1075 (validate channel range)
- [ ] Create migration 1076 (add agent_id to channels)
- [ ] Update Channel.php validation methods
- [ ] Test channel range validation

### Phase 2: Agent ID = Channel Number Mapping
- [ ] Implement direct mapping logic
- [ ] Update channel creation
- [ ] Update channel loading
- [ ] Test direct mapping

### Phase 3: Multi-Participant Support
- [ ] Update participant management
- [ ] Update message system
- [ ] Update channel statistics
- [ ] Test multi-participant conversations

### Phase 4: Multi-Agent Broadcasting
- [ ] Create AgentBroadcast.php class
- [ ] Implement broadcasting system
- [ ] Implement message routing
- [ ] Test multi-agent broadcasting

### Phase 5: WOLFIE Headers Integration
- [ ] Integrate with WOLFIE Headers v2.0.2
- [ ] Update channel resolution
- [ ] Update agent file naming
- [ ] Test integration

---

## NEXT_STEPS

1. **Start with Phase 1** - Database validation and agent_id column
2. **Test Phase 1** - Verify channel range constraints work
3. **Move to Phase 2** - Implement direct mapping
4. **Continue through phases** - Build incrementally

---

**Status**: Ready for implementation  
**Priority**: High (Core Feature for v1.0.0)  
**Estimated Time**: Multi-phase implementation

---

*Captain WOLFIE, signing off. Coffee hot. Ship flying. Channel architecture plan ready. Maximum 999.* ☕✨

