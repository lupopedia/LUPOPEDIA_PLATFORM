---
title: AGENT_LOGGING_GUIDE.md
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
tags: [SYSTEM, DOCUMENTATION, AGENT_LOGGING, DUAL_STORAGE]
collections: [WHAT, WHEN, WHY, HOW, DO]
in_this_file_we_have: [AGENT_LOGGING_PROCESS, WOLFIE_HEADERS_TEMPLATE, LOG_EXAMPLES, DUAL_STORAGE_INTEGRATION]
shadow_aliases: []
parallel_paths: []
---

# Agent Logging Guide

**Version**: v0.1.0  
**Status**: Operational  
**Last Updated**: 2025-11-20

This guide demonstrates how to log agent activities using the WOLFIE Headers 10-section format. All agent actions are logged in dual-storage format: Markdown files (`[channel][agent]log.md`) and database (`content_log` table) for integrity and portability.

---

## WHO

- **Primary Logger**: All agents (WOLFIE 008, VISHWAKARMA 075, LILITH 010, MAAT 009, etc.)
- **System**: LUPOPEDIA Platform logging system
- **Integration**: WOLFIE Headers v2.1.0+ log file system

---

## WHAT

- **Description**: Process for logging agent activities, queries, and interactions
- **Type**: Agent Activity Logging & System Audit
- **Log Format**: `[channel][agent]log.md` (e.g., `channel008_agent008_log.md`)
- **Storage**: Dual-storage (Markdown files + database `content_log` table)
- **Status**: Operational in v0.1.0

---

## WHERE

- **Domain**: lupopedia.com
- **Repository**: github.com/lupopedia/lupopedia_platform
- **Log Files**: `logs/[channel][agent]log.md` or `public/logs/[channel][agent]log.md`
- **Database**: `content_log` table (synced from Markdown files)
- **Viewer**: `captain_log.php` - Multi-agent operational log viewer

---

## WHEN

- **Created**: 2025-11-20
- **Available**: v0.1.0+
- **Logging**: Real-time as agents process queries
- **Sync**: Automatic sync between Markdown files and database

---

## WHY

- **Reason**: Record agent actions for auditing, debugging, and collaborative review
- **Benefits**:
  - Ensures traceability in multi-agent interactions
  - Supports federation by syncing logs across domains
  - Enables "sitcom-style" multi-agent perspectives in Captain's Log
  - Provides dual-storage integrity (file + database)
  - Machine-readable format for analysis and search

---

## HOW

### WOLFIE Headers Template for Agent Logging

Use this template as frontmatter in your agent log files:

```yaml
---
WHO:
  - Agent: {Agent Name} ({Agent ID})
  - Role: {Agent Role}
  - Initiator: {User or Agent that triggered action}
  - Contact: {Contact information if applicable}

WHAT:
  - Description: {What action was performed}
  - Type: Agent Activity Log
  - Event: {Event type: Query Routing, Broadcast, Response, etc.}
  - Status: {Completed, In Progress, Failed, etc.}

WHERE:
  - Domain: lupopedia.com
  - Repository: github.com/lupopedia/lupopedia_platform
  - Channel: {Channel Number}
  - Log File: channel{ID}_agent{ID}_log.md

WHEN:
  - Timestamp: {ISO 8601 timestamp}
  - Duration: {Processing duration}
  - Processed: {Completion timestamp}

WHY:
  - Reason: {Why this action was taken}
  - Benefits: {What this achieves}

HOW:
  - Method: {How the action was performed}
  - Dependencies: {Required systems/components}
  - Steps:
    - {Step 1}
    - {Step 2}
    - {Step 3}

DO:
  - Actions Performed:
    - {Action 1}
    - {Action 2}
    - {Action 3}
  - Output: {Result or output}

HACK:
  - Workarounds: {Fallback options}
  - Risks: {Potential issues}
  - Tips: {Verification commands}

OTHER:
  - Notes: {Additional context}
  - Related: {Related agents, systems, or events}

TAGS:
  - agent-logging
  - activity-log
  - {event-specific-tags}
  - {domain-specific-tags}
  - system-audit
  - wolfie-headers
  - v0.1.0
---
```

### Logging Process

1. **Agent Receives Query**
   - Query arrives on agent's channel
   - Agent reads YAML-wrapped query headers
   - Validates query format

2. **Process Query**
   - Agent performs required actions
   - Routes to other agents if needed (e.g., WOLFIE 008 → 007 → VISH 075)
   - Broadcasts to listening agents

3. **Create Log Entry**
   - Generate WOLFIE Headers frontmatter
   - Add log entry content
   - Save to `[channel][agent]log.md` file

4. **Sync to Database**
   - Automatic sync to `content_log` table
   - Maintains dual-storage integrity
   - Enables search and analysis

5. **Update Captain's Log**
   - Multi-agent perspectives aggregated
   - "Sitcom-style" narrative format
   - Viewable via `captain_log.php`

---

## DO

### Example: WOLFIE (008) Query Processing Log

**Complete WOLFIE Headers Definition**:

```yaml
---
WHO:
  - Agent: WOLFIE (008)
  - Role: System Architect
  - Initiator: Eric Robin Gerdes (Wolfie)
  - Contact: wolfie@lupopedia.com

WHAT:
  - Description: Log entry for processing a user query on channel architecture
  - Type: Agent Activity Log
  - Event: Query Routing and Broadcast
  - Status: Completed

WHERE:
  - Domain: lupopedia.com
  - Repository: github.com/lupopedia/lupopedia_platform
  - Channel: 008
  - Log File: channel008_agent008_log.md

WHEN:
  - Timestamp: 2025-11-20T17:00:00Z
  - Duration: 5 minutes
  - Processed: 2025-11-20T17:05:00Z

WHY:
  - Reason: To record agent actions for auditing, debugging, and collaborative review
  - Benefits: Ensures traceability in multi-agent interactions and supports federation by syncing logs across domains

HOW:
  - Method: Parse incoming YAML-wrapped query, route via RESTful APIs, and broadcast to listening agents
  - Dependencies: Crafty Syntax 3.7.5, WOLFIE Headers 2.1.0
  - Steps:
    - Receive query on Channel 008
    - Read headers and validate
    - Escalate if needed (e.g., to Channel 007, exclusive to Wolfie)
    - Sync log to database (content_log table) and Markdown file

DO:
  - Actions Performed:
    - Routed query to VISHWAKARMA (075) for normalization
    - Broadcasted response to all tuned agents
    - Updated SOT tables for change tracking
  - Output: Synthesized response logged in captain_log.php

HACK:
  - Workarounds: If database sync fails, fallback to file-only storage
  - Risks: Log overflow in high-traffic channels; implement rotation
  - Tips: Use lupopedia.php?cmd=STATUS to check log integrity

OTHER:
  - Notes: This log entry demonstrates WOLFIE Headers for agent-specific logging, ensuring portability and machine-readable format
  - Related: Integration with Agape for behavioral pattern analysis on logged interactions

TAGS:
  - agent-logging
  - activity-log
  - query-processing
  - system-audit
  - wolfie-headers
  - v0.1.0
---

## Log Entry Content

**Query Received**: User query about channel architecture implementation  
**Processing**: Validated YAML headers, routed to VISHWAKARMA (075) for normalization  
**Response**: Channel architecture documentation provided, SOT tables updated  
**Broadcast**: Response broadcasted to all agents tuned to Channel 008

**Crew Commentary**:
- [VISH]: Normalized channel mapping terminology for consistency
- [MAAT]: Verified completeness of channel architecture documentation
- [LILITH]: Reviewed for potential brittleness in direct mapping approach
```

### Verification Steps

1. **Check Log File**
   ```bash
   # View agent log file
   cat logs/channel008_agent008_log.md
   ```

2. **Verify Database Sync**
   ```bash
   # Check content_log table
   SELECT * FROM content_log WHERE channel_id = 008 AND agent_id = 008;
   ```

3. **View Captain's Log**
   ```bash
   # Via web interface
   captain_log.php
   ```

4. **Check Log Integrity**
   ```bash
   # Via command system
   lupopedia.php?cmd=STATUS
   ```

---

## HACK

- **Workarounds**: 
  - If database sync fails, fallback to file-only storage
  - If log files become too large, implement log rotation
  - Use file-based caching if database unavailable

- **Risks**: 
  - Log overflow in high-traffic channels (mitigate with rotation)
  - Database sync failures (fallback to file storage)
  - Log file corruption (maintain backups)

- **Tips**: 
  - Use `lupopedia.php?cmd=STATUS` to check log integrity
  - Monitor log file sizes and implement rotation
  - Regular backups of both Markdown files and database
  - Use Agape for behavioral pattern analysis on logged interactions

---

## OTHER

### Dual-Storage System

**Markdown Files**:
- Format: `[channel][agent]log.md`
- Location: `logs/` or `public/logs/`
- Purpose: Human-readable, portable, version-controllable

**Database**:
- Table: `content_log`
- Purpose: Searchable, queryable, analyzable
- Sync: Automatic from Markdown files

**Benefits**:
- Integrity: Dual storage prevents data loss
- Portability: Markdown files travel across domains
- Searchability: Database enables fast queries
- Federation: Logs sync across domains

### Multi-Agent Logging

**Overlapping Chatter**:
- Multiple agents log simultaneously
- Creates "multi-voice chorus" effect
- Intentional chaos for sitcom-style logs
- Example: WOLFIE (008), VISH (075), and LILITH (010) all log same event from different perspectives

**Captain's Log Integration**:
- Aggregates all agent logs
- Creates narrative from multi-agent perspectives
- Maintains sitcom-style humor
- Viewable via `captain_log.php`

### Related Documentation

- `docs/WOLFIE_HEADERS_INTEGRATION.md` - WOLFIE Headers log system
- `captain_log.php` - Multi-agent log viewer
- `docs/AGENT_COMMUNICATION_PROTOCOL.md` - Agent routing and logging
- `todo_for_version_1_0_0.md` - Log system improvements planned

---

## TAGS

- agent-logging
- activity-log
- dual-storage
- system-audit
- wolfie-headers
- v0.1.0
- federation
- portability

---

**Last Updated**: 2025-11-20  
**Documentation Version**: 1.0  
**Platform Version**: v0.1.0

