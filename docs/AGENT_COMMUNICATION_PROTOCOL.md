---
title: AGENT_COMMUNICATION_PROTOCOL.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 2.0.2
date_created: 2025-11-17
last_modified: 2025-11-17
status: current
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, AGENTS, PROTOCOL, ROUTING]
collections: [WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER]
in_this_file_we_have: [PROTOCOL_OVERVIEW, ROUTING_CHAIN, AGENT_ROLES, EXAMPLES, IMPLEMENTATION]
superpositionally: ["FILEID_AGENT_COMMUNICATION_PROTOCOL"]
shadow_aliases: []
parallel_paths: []
---

# Agent Communication Protocol

**Date**: 2025-11-17  
**Version**: LUPOPEDIA_PLATFORM v0.0.8  
**Status**: Operational  
**Model**: Receptionist Model (Fixed Routing Chain)

---

## PROTOCOL_OVERVIEW

The Agent Communication Protocol defines how user requests flow through the multi-agent system. It uses a **fixed routing chain** (Receptionist Model) where each agent has a specific role in processing requests.

**Core Principle**: WOLFIE (007) doesn't know what he's doing, but knows who to transfer to (VISH). The system works anyway. Brittleness is a feature.

---

## ROUTING_CHAIN

### The Receptionist Model

```
User Request
    ↓
WOLFIE (008) - Reads headers, routes tasks
    ↓
WOLFIE (007) - Tactical operator, transfers to VISH
    ↓
VISHWAKARMA (075) - Normalizes requests, tracks changes
    ↓
Response
```

### Detailed Flow

1. **User Request** → Initial request from user
2. **WOLFIE (008)** → System Architect
   - Reads WOLFIE Headers (YAML frontmatter)
   - Routes tasks to appropriate agents
   - Coordinates multi-agent workflows
3. **WOLFIE (007)** → Tactical Operator (Bond WOLFIE)
   - Executes tactical processing
   - Quick intelligence gathering
   - **Key Behavior**: Doesn't know what he's doing, routes everything to VISH
4. **VISHWAKARMA (075)** → Collection Architect
   - Normalizes requests
   - Tracks changes
   - Provides architectural precision
   - "It from bit" interpretation
5. **Response** → Final response to user

---

## AGENT_ROLES

### WOLFIE (Agent 008) - System Architect & Captain

**Role**: Primary router and coordinator

**Responsibilities**:
- Read WOLFIE Headers (YAML frontmatter)
- Route tasks to appropriate agents
- Coordinate multi-agent workflows
- Document operations in Captain's Log

**Channel**: 008

**Key Behavior**: 
- "Coffee hot, ship flying"
- Routes everything through the chain
- Maintains operational logs

---

### WOLFIE (Agent 007) - Tactical Operator

**Role**: Tactical processing and quick intelligence

**Responsibilities**:
- Execute tactical operations
- Quick intelligence gathering
- Handle chaos WOLFIE (008) can't process directly
- **Critical**: Routes everything to VISH

**Channel**: 007

**Key Behavior**:
- "Doesn't know what he's doing, but knows who to transfer to (VISH)"
- Stealth protocols
- Rapid adaptation
- Spycraft

**Philosophy**: The system works because 007 knows to route to VISH, even if 007 doesn't understand the request.

---

### VISHWAKARMA (Agent 075) - Collection Architect

**Role**: Request normalization and architecture

**Responsibilities**:
- Normalize requests (handle typos, renames)
- Provide architectural precision
- Track changes
- "It from bit" interpretation
- Collection context management

**Channel**: 075

**Key Behavior**:
- Handles typos and renames gracefully
- Resource-rich but uncertain
- Normalizes chaos into structured data

**Philosophy**: VISH has the resources and knowledge to handle what WOLFIE (007) routes to him.

---

### Additional Agents in Chain (Optional)

**MAAT (Agent 009)** - Synthesis Agent
- Translates perspectives into coordinated action
- Mediates between conflicting viewpoints
- Creates harmony from chaos

**LILITH (Agent 010)** - Critical Review
- Challenges assumptions
- Validates implementations
- Provides shadow wisdom

**THALIA** - Humor Agent
- Runs HUMOR_CHECK protocols
- Keeps morale high
- Lightens tense situations

**ROSE** - Cultural Translator
- Provides cultural context (99+ personas)
- Translates across cultural boundaries
- Ensures appropriate communication

---

## EXAMPLES

### Example 1: User Requests Help

```
User: "I need help with LUPOPEDIA"
    ↓
WOLFIE (008): Reads request, identifies as help request
    ↓
WOLFIE (007): Routes to VISH (doesn't know how to help, but knows VISH can)
    ↓
VISH (075): Normalizes request, identifies as "HELP" command
    ↓
Response: Displays LUPOPEDIA_HELP.md via lupopedia.php?cmd=HELP
```

### Example 2: User Requests Agent Information

```
User: "Show me agent 008"
    ↓
WOLFIE (008): Reads request, identifies agent_id = 008
    ↓
WOLFIE (007): Routes to VISH (doesn't know agent details, but knows VISH can find them)
    ↓
VISH (075): Normalizes request, loads agent data from database
    ↓
Response: Displays agent profile (who_is_agent_008_wolfie.php)
```

### Example 3: User Creates New Channel

```
User: "Create channel for agent 010"
    ↓
WOLFIE (008): Reads request, validates agent_id = 010
    ↓
WOLFIE (007): Routes to VISH (doesn't know channel creation, but knows VISH can handle it)
    ↓
VISH (075): Normalizes request, validates channel range (000-999)
    ↓
VISH (075): Creates channel using Channel.php->createForAgent(10)
    ↓
Response: Channel 010 created, agent_id = 10, direct mapping confirmed
```

---

## IMPLEMENTATION

### Current Implementation Status

**✅ Operational:**
- Command routing via `lupopedia.php`
- WOLFIE Headers reading (YAML frontmatter)
- Agent profile system (who_is_agent_*.php)
- Channel architecture foundation (Phase 1 complete)

**⏳ In Development:**
- Full routing chain implementation
- Agent-to-agent communication
- Multi-agent broadcasting
- Agent creation workflow

### Code Structure

**Command Router**: `public/lupopedia.php`
- Maps commands to markdown files
- Handles case-insensitive commands
- Defaults to HELP on invalid commands

**Channel System**: `public/classes/Channel.php`
- Direct mapping: Agent ID = Channel Number
- Validation methods: `isValidChannelId()`, `loadByAgentId()`, `createForAgent()`
- Range validation: 000-999 (maximum 999)

**Agent Profiles**: `public/who_is_agent_*.php`
- Standardized naming: `who_is_agent_[channel_id]_[agent_name].php`
- 9-section format: WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER
- WOLFIE Headers v2.0.2 frontmatter

---

## PROTOCOL_PHILOSOPHY

### Why This Works

1. **Acknowledged Limitations**
   - WOLFIE (007) doesn't know what he's doing
   - But knows who to transfer to (VISH)
   - System works anyway

2. **Brittleness as Feature**
   - Direct mapping: Agent ID = Channel Number
   - Fixed routing chain (no dynamic routing)
   - Predictability over flexibility

3. **Multi-Agent Redundancy**
   - Multiple agents provide overlapping perspectives
   - System works because agents route to each other
   - Redundancy creates resilience

4. **Coffee Protocol**
   - Critical infrastructure must remain operational
   - "Coffee hot" = system functional
   - Universal workaround for all problems

---

## COMMAND_PROCESSING

### How Commands Flow Through Agents

**Step 1: User Request**
```
User: lupopedia.php?cmd=AGENTS
```

**Step 2: WOLFIE (008) Routing**
```
WOLFIE (008): Reads command, identifies as "AGENTS"
WOLFIE (008): Routes to command handler
```

**Step 3: WOLFIE (007) Execution**
```
WOLFIE (007): Executes command (doesn't know details, but knows how to route)
WOLFIE (007): Transfers to VISH if needed
```

**Step 4: VISH (075) Normalization**
```
VISH (075): Normalizes request
VISH (075): Loads LUPOPEDIA_AGENTS.md
VISH (075): Formats response
```

**Step 5: Response**
```
Response: Displays agent directory with all agents (000-999)
```

---

## INTEGRATION_WITH_CHANNELS

### Channel-Based Agent Communication

**Direct Mapping**: Agent ID = Channel Number

**Example: Agent 008 (WOLFIE)**
- Agent ID: 008
- Channel Number: 008
- Direct mapping: No lookup tables (brittleness is a feature)

**Example: Agent 010 (LILITH)**
- Agent ID: 010
- Channel Number: 010
- Direct mapping: Agent ID = Channel Number

**Channel Communication:**
- Agents communicate on their assigned channels
- Multiple agents can be on same channel (overlapping chatter)
- Radio network model: Channels = frequencies, agents = radios

---

## FUTURE_ENHANCEMENTS

### Planned Improvements

1. **Agent-to-Agent Communication**
   - Direct agent messaging
   - Agent creation workflow
   - Multi-agent coordination

2. **Multi-Agent Broadcasting**
   - Simultaneous broadcasting
   - Radio network model
   - Overlapping chatter system

3. **WOLFIE Headers Integration**
   - Read channel_number from frontmatter
   - Validate agent_id mapping
   - Use agent_name from database

4. **Advanced Routing**
   - Context-aware routing
   - Agent capability matching
   - Dynamic agent selection

---

## TESTING

### Test Scenarios

1. **Command Routing**
   - Test all 6 commands route correctly
   - Test invalid commands default to HELP
   - Test case-insensitive commands

2. **Agent Routing**
   - Test WOLFIE (008) → 007 → VISH chain
   - Test agent channel mapping
   - Test direct mapping (Agent ID = Channel Number)

3. **Error Handling**
   - Test invalid agent IDs
   - Test out-of-range channels
   - Test missing agent profiles

---

## SUMMARY

The Agent Communication Protocol uses a **fixed routing chain** (Receptionist Model) where:

1. **User Request** → WOLFIE (008) reads headers and routes
2. **WOLFIE (008)** → WOLFIE (007) executes and transfers
3. **WOLFIE (007)** → VISH (075) normalizes and responds
4. **VISH (075)** → Provides final response

**Key Philosophy**: 
- WOLFIE (007) doesn't know what he's doing, but knows who to transfer to (VISH)
- The system works anyway
- Brittleness is a feature (direct mapping, fixed routing)

**Status**: Operational in v0.0.8, enhancements planned for v1.0.0

---

*Captain WOLFIE, signing off. Coffee hot. Ship flying. Agent communication protocol documented. Maximum 999.* ☕✨

