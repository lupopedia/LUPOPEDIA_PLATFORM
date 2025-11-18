---
title: FUNCTIONAL_COMMANDS_REFERENCE.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 2.0.2
date_created: 2025-11-17
last_modified: 2025-11-17
status: current
onchannel: 1
tags: [SYSTEM, COMMANDS, REFERENCE, v0.0.8]
collections: [WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER]
in_this_file_we_have: [COMMAND_ROUTER, AVAILABLE_COMMANDS, USAGE_EXAMPLES, QUICK_ACCESS]
superpositionally: ["FILEID_FUNCTIONAL_COMMANDS_REFERENCE"]
shadow_aliases: []
parallel_paths: []
---

# LUPOPEDIA Functional Commands Reference (v0.0.8)

**Date**: 2025-11-17  
**Version**: LUPOPEDIA_PLATFORM v0.0.8  
**Status**: ✅ Operational  
**Command Router**: `lupopedia.php`

---

## COMMAND_ROUTER

**Base URL**: `lupopedia.php?cmd=COMMAND`

**Default Command**: `HELP` (if no command specified or invalid command)

**Command Format**: Uppercase (automatically converted)

---

## AVAILABLE_COMMANDS

### 1. HELP

**Command**: `lupopedia.php?cmd=HELP`  
**File**: `LUPOPEDIA_HELP.md`  
**Purpose**: General help information and overview  
**Status**: ✅ Operational

**Description**:  
Provides general help information, quick start guide, and overview of the LUPOPEDIA system.

---

### 2. COMMANDS

**Command**: `lupopedia.php?cmd=COMMANDS`  
**File**: `LUPOPEDIA_COMMANDS.md`  
**Purpose**: Command reference and list  
**Status**: ✅ Operational

**Description**:  
Lists all available commands with descriptions and usage examples.

---

### 3. AGENTS

**Command**: `lupopedia.php?cmd=AGENTS`  
**File**: `LUPOPEDIA_AGENTS.md`  
**Purpose**: Agent directory (all agents 000-999)  
**Status**: ✅ Operational

**Description**:  
Displays agent directory with all agents (000-999), their roles, channels, and 9-category format (WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER).

---

### 4. STATUS

**Command**: `lupopedia.php?cmd=STATUS`  
**File**: `LUPOPEDIA_STATUS.md`  
**Purpose**: System status and health check  
**Status**: ✅ Operational

**Description**:  
Shows current system status, version information, dependency status, and operational health.

---

### 5. CAPTAIN_LOG

**Command**: `lupopedia.php?cmd=CAPTAIN_LOG`  
**File**: `LUPOPEDIA_CAPTAIN_LOG.md`  
**Purpose**: Operational log and development history  
**Status**: ✅ Operational

**Description**:  
Displays the Captain's Log with multi-agent perspectives, development history, and sitcom-style operational tracking.

---

### 6. PLATFORM_HELP

**Command**: `lupopedia.php?cmd=PLATFORM_HELP`  
**Alias**: `lupopedia.php?cmd=PLATFORM`  
**File**: `LUPOPEDIA_PLATFORM_HELP.md`  
**Purpose**: Platform-specific help and documentation  
**Status**: ✅ Operational

**Description**:  
Comprehensive platform documentation including architecture, dependencies, channel system, agent system, and development roadmap.

---

## USAGE_EXAMPLES

### Basic Usage

```bash
# General help
lupopedia.php?cmd=HELP

# Command reference
lupopedia.php?cmd=COMMANDS

# Agent directory
lupopedia.php?cmd=AGENTS

# System status
lupopedia.php?cmd=STATUS

# Captain's Log
lupopedia.php?cmd=CAPTAIN_LOG

# Platform help
lupopedia.php?cmd=PLATFORM_HELP
# or
lupopedia.php?cmd=PLATFORM
```

### Error Handling

- Invalid commands default to `HELP`
- Missing files show error message
- Commands are case-insensitive (automatically converted to uppercase)

---

## QUICK_ACCESS_FILES

In addition to the command router, these files are directly accessible:

- **`help.php`** - Comprehensive platform documentation
- **`captain_log.php`** - Operational log viewer
- **`howto.php`** - Complete LUPOPEDIA guide

---

## COMMAND_MAPPING

The command router uses the following mapping:

```php
$commandMap = [
    'HELP' => 'LUPOPEDIA_HELP.md',
    'COMMANDS' => 'LUPOPEDIA_COMMANDS.md',
    'AGENTS' => 'LUPOPEDIA_AGENTS.md',
    'STATUS' => 'LUPOPEDIA_STATUS.md',
    'CAPTAIN_LOG' => 'LUPOPEDIA_CAPTAIN_LOG.md',
    'PLATFORM_HELP' => 'LUPOPEDIA_PLATFORM_HELP.md',
    'PLATFORM' => 'LUPOPEDIA_PLATFORM_HELP.md', // Alias
];
```

---

## TECHNICAL_DETAILS

**Router File**: `public/lupopedia.php`  
**Markdown Files**: `public/LUPOPEDIA_*.md`  
**Markdown to HTML**: Basic conversion included in router  
**Error Handling**: Defaults to HELP on invalid commands  
**Case Sensitivity**: Commands converted to uppercase automatically

---

## STATUS_SUMMARY

| Command | Status | File Exists | Operational |
|---------|--------|-------------|-------------|
| HELP | ✅ | ✅ | ✅ |
| COMMANDS | ✅ | ✅ | ✅ |
| AGENTS | ✅ | ✅ | ✅ |
| STATUS | ✅ | ✅ | ✅ |
| CAPTAIN_LOG | ✅ | ✅ | ✅ |
| PLATFORM_HELP | ✅ | ✅ | ✅ |

**Total Commands**: 6 (all operational)  
**Version**: v0.0.8 (Functional Command System)

---

## AGENT_COMMUNICATION_PROTOCOL

### How Commands Are Processed

All commands flow through the **Agent Communication Protocol** (Receptionist Model):

```
User Request (lupopedia.php?cmd=COMMAND)
    ↓
WOLFIE (008) - Reads command, routes to handler
    ↓
WOLFIE (007) - Executes command, transfers to VISH if needed
    ↓
VISH (075) - Normalizes request, loads markdown file
    ↓
Response - Displays formatted content
```

**Key Behavior**: WOLFIE (007) doesn't know what he's doing, but knows who to transfer to (VISH). The system works anyway.

**For detailed protocol documentation**, see: `docs/AGENT_COMMUNICATION_PROTOCOL.md`

---

*Captain WOLFIE, signing off. Coffee hot. Ship flying. Commands operational. Maximum 999.* ☕✨

