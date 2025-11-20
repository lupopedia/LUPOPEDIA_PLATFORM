---
title: AGENT_SPAWNING_GUIDE.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 0.1.0
wolfie_headers_version: 2.1.0
crafty_syntax_version: 3.8.0
date_created: 2025-11-20
last_modified: 2025-11-20
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, AGENT_CREATION, AGENT_SPAWNING]
collections: [WHAT, WHEN, WHY, HOW, DO]
in_this_file_we_have: [AGENT_SPAWNING_PROCESS, WOLFIE_HEADERS_TEMPLATE, SPAWNING_EXAMPLES, INTEGRATION_DETAILS]
shadow_aliases: []
parallel_paths: []
---

# Agent Spawning Guide

**Version**: v0.1.0  
**Status**: Operational  
**Last Updated**: 2025-11-20

This guide demonstrates how to spawn new agents using the WOLFIE Headers 10-section format. Agents can create other agents, enabling the platform to expand its capabilities dynamically.

---

## WHO

- **Name**: System Architect / Agent Creator
- **Primary Spawner**: WOLFIE (008) - Core agent initiating spawns
- **Approval Chain**: WOLFIE (008) → WOLFIE (007) → VISHWAKARMA (075)
- **Note**: Channel 007 is exclusive to Eric Robin Gerdes (Wolfie) - see `docs/CHANNEL_007_RESERVATION.md`

---

## WHAT

- **Description**: Process for creating new specialist agents to expand platform capabilities
- **Type**: Agent Creation & System Expansion
- **Agent ID Range**: 000-999 (excluding 007, which is reserved)
- **Naming Convention**: `who_is_agent_{ID}_{name}.php`
- **Status**: Operational in v0.1.0

---

## WHERE

- **Domain**: lupopedia.com
- **Repository**: github.com/lupopedia/lupopedia_platform
- **Channel Assignment**: Agent ID = Channel Number (direct mapping)
- **Files**:
  - `who_is_agent_{ID}_{name}.php` - Agent spawning script
  - `docs/AGENT_COMMUNICATION_PROTOCOL.md` - Routing chain documentation
  - `content_log` table - Agent registration database

---

## WHEN

- **Created**: 2025-11-20
- **Available**: v0.1.0+
- **Activation**: Immediate upon successful spawn
- **Review Cycle**: Per agent lifecycle management

---

## WHY

- **Reason**: Enable dynamic system expansion through agent self-creation
- **Benefits**:
  - Specialized expertise for emerging domains (e.g., quantum ethics, AI governance)
  - Enhanced federation capabilities
  - Improved collaborative synthesis across channels
  - Platform adapts to new knowledge domains automatically
- **Philosophy**: "Agents making agents" - the system evolves organically

---

## HOW

### WOLFIE Headers Template for Agent Spawning

Use this template as frontmatter in your agent spawning script:

```yaml
---
WHO:
  - Name: {Agent Name}
  - Alias: {Agent Alias}
  - Role: {Specialist Role}
  - Spawner: WOLFIE (008)  # The core agent initiating the spawn

WHAT:
  - Description: {Agent purpose and capabilities}
  - Type: Agent Creation
  - Agent ID: {000-999, excluding 007}
  - Name: {AGENT_NAME}
  - Status: Initialization

WHERE:
  - Domain: lupopedia.com
  - Repository: github.com/lupopedia/lupopedia_platform
  - Channel: {Agent ID}
  - File: who_is_agent_{ID}_{name}.php

WHEN:
  - Created: {ISO 8601 timestamp}
  - Spawn Time: {Planned spawn timestamp}
  - Activation Deadline: {Target activation date}

WHY:
  - Reason: {Why this agent is needed}
  - Benefits: {What capabilities it adds}

HOW:
  - Method: WOLFIE Headers + RESTful API call from WOLFIE (008)
  - Dependencies: Crafty Syntax 3.7.5+, WOLFIE Headers 2.1.0+, LUPOPEDIA Core
  - Steps:
    - Validate agent ID availability
    - Broadcast spawn request on Channel 008
    - Map new agent to channel and log in content_log table

DO:
  - Actions:
    - Escalate to WOLFIE (007) for tactical approval
    - Integrate with existing routing chain
    - Test initial broadcast response
  - Output: New agent configuration file and database entry

HACK:
  - Workarounds: {Fallback options if channel conflicts}
  - Risks: {Potential issues}
  - Tips: {Verification commands}

OTHER:
  - Notes: {Additional context}
  - Related: {Related agents or systems}

TAGS:
  - agent-spawning
  - new-agent
  - {domain-specific-tags}
  - system-expansion
  - wolfie-headers
  - v0.1.0
---
```

### Spawning Process

1. **Validate Agent ID**
   - Check that Agent ID is available (000-999, excluding 007)
   - Verify no existing agent uses the ID
   - Confirm channel mapping is available

2. **Create WOLFIE Headers Definition**
   - Use template above with agent-specific details
   - Include all 10 sections (WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER, TAGS)
   - Save as frontmatter in spawning script

3. **Broadcast Spawn Request**
   - WOLFIE (008) broadcasts spawn request on Channel 008
   - Request includes WOLFIE Headers definition
   - System validates request

4. **Tactical Approval**
   - Escalate to WOLFIE (007) for approval (if required)
   - Note: Channel 007 is exclusive - approval may be automatic for other channels

5. **Agent Registration**
   - Create `who_is_agent_{ID}_{name}.php` file
   - Register agent in `content_log` table
   - Map Agent ID to Channel Number (direct mapping)

6. **Integration**
   - Integrate with routing chain: WOLFIE (008) → {New Agent} → VISHWAKARMA (075)
   - Test initial broadcast response
   - Verify agent appears in `lupopedia.php?cmd=AGENTS`

---

## DO

### Example: Spawning QUANTUM_ETHOS Agent (Channel 050)

**Complete WOLFIE Headers Definition**:

```yaml
---
WHO:
  - Name: QUANTUM_ETHOS
  - Alias: Quantum Ethics Specialist
  - Role: Specialist Agent for Quantum Computing Ethics
  - Spawner: WOLFIE (008)

WHAT:
  - Description: Spawn a new specialist agent for handling quantum computing ethics discussions
  - Type: Agent Creation
  - Agent ID: 050
  - Name: QUANTUM_ETHOS
  - Status: Initialization

WHERE:
  - Domain: lupopedia.com
  - Repository: github.com/lupopedia/lupopedia_platform
  - Channel: 050
  - File: who_is_agent_050_quantum_ethos.php

WHEN:
  - Created: 2025-11-20T16:00:00Z
  - Spawn Time: 2025-11-20T16:15:00Z
  - Activation Deadline: 2025-11-25T00:00:00Z

WHY:
  - Reason: To expand the platform's capabilities in emerging tech ethics, allowing specialized handling of quantum-related queries
  - Benefits: Enhances federation by adding domain-specific expertise, improves collaborative synthesis in related channels

HOW:
  - Method: Use WOLFIE Headers to define agent properties, then execute spawning script via RESTful API call from WOLFIE (008)
  - Dependencies: Crafty Syntax 3.7.5, WOLFIE Headers 2.1.0, LUPOPEDIA Core
  - Steps:
    - Validate agent ID availability (050 is available)
    - Broadcast spawn request on Channel 008
    - Map new agent to channel and log in content_log table

DO:
  - Actions:
    - Escalate to WOLFIE (007) for tactical approval (exclusive channel use noted)
    - Integrate with existing routing chain
    - Test initial broadcast response
  - Output: New agent configuration file and database entry

HACK:
  - Workarounds: If channel mapping conflicts, fallback to next available ID (e.g., 051)
  - Risks: Potential overlap in multi-agent broadcasts if not isolated properly
  - Tips: Run lupopedia.php?cmd=AGENTS to list and verify after spawn

OTHER:
  - Notes: This YAML serves as frontmatter for the spawning script, ensuring portability across domains. New agents inherit core behaviors but specialize per definition.
  - Related: Integration with Agape for behavioral analysis post-spawn

TAGS:
  - agent-spawning
  - new-agent
  - quantum-ethics
  - system-expansion
  - wolfie-headers
  - v0.1.0
---
```

### Verification Steps

1. **Check Agent Directory**
   ```bash
   # Via command system
   lupopedia.php?cmd=AGENTS
   ```

2. **Verify Channel Mapping**
   ```bash
   # Check channel assignment
   lupopedia.php?cmd=STATUS
   ```

3. **Test Broadcast**
   - Send test query to Channel 050
   - Verify QUANTUM_ETHOS responds
   - Check routing chain integration

4. **Review Logs**
   - Check `captain_log.php` for spawn event
   - Verify `content_log` table entry
   - Review agent communication protocol logs

---

## HACK

- **Workarounds**: 
  - If channel mapping conflicts, use next available ID
  - If WOLFIE (007) approval delayed, use automatic approval for non-critical agents
  - Fallback to manual agent creation if automated spawn fails

- **Risks**: 
  - Potential overlap in multi-agent broadcasts if not isolated properly
  - Channel conflicts if ID validation fails
  - Agent proliferation without governance (mitigated by lifecycle management)

- **Tips**: 
  - Always run `lupopedia.php?cmd=AGENTS` to verify after spawn
  - Check `captain_log.php` for spawn confirmation
  - Test agent response before marking as active
  - Use Agape for behavioral analysis post-spawn

---

## OTHER

### Agent Specialization Examples

**AI Governance Specialist (Channel 042)**:
- Focus: AI ethics, governance frameworks, policy analysis
- Tags: ai-governance, ethics, policy-analysis

**Cultural Translation Specialist (Channel 075 - VISHWAKARMA)**:
- Focus: Cross-cultural communication, cultural context
- Tags: cultural-translation, communication, context

**Humor & Light Specialist (Channel 099 - THALIA)**:
- Focus: Injecting humor, maintaining light atmosphere
- Tags: humor, sitcom-style, light-commentary

### Integration with Agent DNA System

- New agents can inherit DNA from Agent 001 (UNKNOWN) as primordial template
- DNA mutations can occur during spawn based on system needs
- Lifecycle hooks log agent birth events to Captain's Log
- See `todo_for_version_1_0_0.md` for DNA system implementation details

### Related Documentation

- `docs/AGENT_COMMUNICATION_PROTOCOL.md` - Routing chain details
- `docs/CHANNEL_007_RESERVATION.md` - Channel 007 exclusivity
- `docs/CHANNEL_ARCHITECTURE_IMPLEMENTATION_PLAN.md` - Channel system architecture
- `todo_for_version_1_0_0.md` - Agent DNA system and lifecycle management

---

## TAGS

- agent-spawning
- agent-creation
- system-expansion
- wolfie-headers
- v0.1.0
- agent-lifecycle
- multi-agent-system
- federation

---

**Last Updated**: 2025-11-20  
**Documentation Version**: 1.0  
**Platform Version**: v0.1.0

