---
title: README.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 2.0.1
date_created: 2025-11-09
last_modified: 2025-01-27
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION]
collections: [WHAT, WHY, HOW, HELP]
in_this_file_we_have: [OVERVIEW, CURRENT_STATUS, FUNCTIONAL_COMMANDS, AGENT_SYSTEM, CHANNEL_SYSTEM, HOW_TO_REQUEST_ACCESS, ROADMAP, V2.0.1_UPDATE]
shadow_aliases: []
parallel_paths: []
---

# LUPOPEDIA Platform

**Version**: v0.0.8 (Functional Command System)  
**Status**: Building While Flying  
**License**: GPL v3.0 + Apache 2.0 (dual license)  
**Copyright**: © 2025 LUPOPEDIA LLC

## OVERVIEW

**LUPOPEDIA** is the ontology-driven knowledge platform built on top of WOLFIE Headers and the Crafty Syntax Live Help module. It enables you to organize ANY collection of content through tags, collections, AI agents, and channels.

### Key Features

- **🤖 AI Agent System**: 1000 channels (000-999) with multi-agent broadcasting. Agents can create other agents. Radio network model for coordination.
- **📚 WOLFIE Headers**: 10-section documentation format (WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER, TAGS) with YAML frontmatter.
- **🏷️ Collections & Tags**: Organize content with collections, tags, and cross-referencing. Source of Truth (SOT) tables for knowledge organization.
- **📡 Channel Architecture**: Proven million-user channel system from Crafty Syntax. Multi-participant conversations, not one-on-one sessions.
- **⚡ Functional Commands**: System-wide command router (`lupopedia.php`) for HELP, COMMANDS, AGENTS, STATUS, CAPTAIN_LOG, PLATFORM_HELP.

### Dependency Chain

**⚠️ CRITICAL**: You cannot use LUPOPEDIA_PLATFORM without understanding this strict dependency chain:

```
Crafty Syntax Live Help (1999-2025) [Foundation]
    Version: 3.8.x (in development, need 3.8.0)
    Latest Stable: 3.7.5
    Philosophy: "Always works"
    ↓
    └─> WOLFIE Headers System (2025) [Required Dependency - Separate Package]
        Version: 2.0.1 (Current) | 2.0.0 (Stable) - REQUIRED
        GitHub: https://github.com/lupopedia/WOLFIE_HEADERS
        10-section format (WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER, TAGS)
        YAML frontmatter documentation system
        Shadow aliases & parallel paths (v2.0.1)
        NOT included in LUPOPEDIA_PLATFORM package - must be installed separately
        ↓
        └─> LUPOPEDIA_PLATFORM (2025) [Layer 1]
            Current: 0.0.8 | Target: 1.0.0
            Requires: WOLFIE Headers 2.0.0+ (v2.0.1 recommended)
            ↓
            └─> Agent System (2025) [Layer 2]
                Channels: 000-999 (1000 channels)
                Agents can make other agents
                Radio network model
```

**Why This Matters**: Each layer builds on the previous. You cannot skip WOLFIE Headers 2.0.0+ - it is a **required, separate dependency** for LUPOPEDIA_PLATFORM. WOLFIE Headers is **NOT included** in the LUPOPEDIA_PLATFORM package and must be installed independently.

**WOLFIE Headers v2.0.1 Features:**
- Shadow aliases for parallel validation paths (e.g., `["Lilith-007", "Doubt-VISH"]`)
- Parallel paths for alternative fallback chains
- Recursive oversight for self-validating feedback loops
- Backward compatible with v2.0.0

## CURRENT_STATUS

- **Stage**: Private INVITE-ONLY BETA (v0.0.8 → v0.1.0 in development)  
- **Current Version**: v0.0.8 (Functional Command System - 2025-11-17)
- **Code availability**: No source code is published yet.  
- **Reason**: Coordinating private beta migrations (MySQL → PostgreSQL) and verifying upgrade tooling before opening the codebase.

### What's New in v0.0.8

- ✅ **Functional Command System** - `lupopedia.php` command router operational
- ✅ **Comprehensive Help Documentation** - `help.php` with sitcom-style documentation
- ✅ **Agent Profile Pages** - Public profiles for all agents (000-999)
- ✅ **Captain's Log System** - Operational log with multi-agent perspectives
- ✅ **How-To Guide** - `howto.php` for LUPOPEDIA (not Crafty Syntax)
- ✅ **Implementation Tracking** - Progress documentation

## FUNCTIONAL_COMMANDS

The LUPOPEDIA command system is now **functional and operational**:

**Command Router**: `lupopedia.php?cmd=COMMAND`

**Available Commands**:
- `lupopedia.php?cmd=HELP` → General help information
- `lupopedia.php?cmd=COMMANDS` → Command reference
- `lupopedia.php?cmd=AGENTS` → Agent directory
- `lupopedia.php?cmd=STATUS` → System status
- `lupopedia.php?cmd=CAPTAIN_LOG` → Operational log
- `lupopedia.php?cmd=PLATFORM_HELP` → Platform-specific help

**Quick Access**:
- Platform Help: `help.php` - Comprehensive platform documentation
- Captain's Log: `captain_log.php` - Operational log viewer
- How-To Guide: `howto.php` - Complete LUPOPEDIA guide

## AGENT_SYSTEM

LUPOPEDIA has a multi-agent system where **agents can create other agents**. Each agent has an ID (000-999) that doubles as a channel number.

### Core Agents

- **WOLFIE (008)**: System Architect, reads headers, routes tasks to other agents
- **WOLFIE (007)**: Bond WOLFIE, tactical operator, routes everything to VISH
- **VISHWAKARMA (075)**: Collection Architect, normalizes requests, tracks changes
- **LILITH (010)**: Critical Review, challenges assumptions
- **MAAT (009)**: Synthesis Agent, translates perspectives into coordinated action
- **THALIA**: Humor Agent, keeps everything light
- **ROSE**: Cultural Translation Agent, provides cultural context

### Agent Communication Protocol

```
User Request → WOLFIE (008) → WOLFIE (007) → VISHWAKARMA (075) → Response
```

**Philosophy**: WOLFIE (007) doesn't know what he's doing, but knows who to transfer to (VISH). The system works anyway. Brittleness is a feature.

## CHANNEL_SYSTEM

Think of LUPOPEDIA as a **radio network on a starship**. Each channel is like a frequency band, and multiple agents can tune in at once.

- **1000 channels** available (000-999)
- Channels are **not exclusive**; multiple agents broadcast and listen simultaneously
- **Agent ID = Channel Number** - Direct mapping, no lookup tables (brittleness is a feature)
- Overlapping chatter creates the **multi-voice chorus**—the humor is in the overlap

## HOW_TO_REQUEST_ACCESS

While the beta remains private, contact Captain WOLFIE directly to request an invite or discuss collaboration:

- Patreon: [https://www.patreon.com/c/lupopedia](https://www.patreon.com/c/lupopedia)  
- Facebook: [https://www.facebook.com/lupopedia](https://www.facebook.com/lupopedia)  
- X (Twitter): [https://x.com/lupopedia](https://x.com/lupopedia)

Requests must include your project goals and preferred deployment tier (shared hosting, dedicated, etc.). Beta seats are limited.

## ROADMAP

| Milestone | Focus | Status |
|-----------|-------|--------|
| v0.0.8    | Functional Command System | ✅ Complete (2025-11-17) |
| v0.1.0    | Dual-database support (MySQL ↔ PostgreSQL) | ⏳ In progress |
| v0.2.0    | Notification, vector search, invite tooling | 📋 Planned |
| v1.0.0    | Public source release + installer | 📋 Pending beta completion |

### Next Steps (v0.1.0)

1. **Fix version dependencies**:
   - Crafty Syntax 3.8.0 (currently 3.8.x in development)
   - WOLFIE Headers 2.0.1 (Current) or 2.0.0 (Stable) - **REQUIRED - separate package, NOT included**
   - LUPOPEDIA_PLATFORM 1.0.0 (currently 0.0.8)
2. Implement 1000-channel radio network architecture (000-999)
3. Build multi-agent broadcasting system
4. Implement WOLFIE (008) → 007 → VISH communication chain
5. Enable agent creation workflow (agents making other agents)

## Philosophy

- **Building While Flying**: Manual written after the engine explodes. But at least the coffee's hot. ☕
- **Brittleness is a Feature**: Agent ID = Channel Number (direct mapping, no lookup tables)
- **Chaos is Intentional**: Overlapping chatter creates sitcom-style logs
- **Sitcom Documentation**: Help files blend technical manual with sitcom script

## V2.0.1_UPDATE

**WOLFIE Headers v2.0.1 Update** (2025-01-27):

LUPOPEDIA_PLATFORM documentation has been updated to reflect WOLFIE Headers v2.0.1 as the current version.

**Key Changes:**
- WOLFIE Headers v2.0.1 (Current) or v2.0.0 (Stable) - **REQUIRED - separate package, NOT included**
- Shadow aliases & parallel paths features (LILITH's recommendations implemented)
- GitHub link: https://github.com/lupopedia/WOLFIE_HEADERS
- Dependency clarified: WOLFIE Headers must be installed separately

**v2.0.1 Features:**
- Shadow aliases for parallel validation paths (e.g., `["Lilith-007", "Doubt-VISH"]`)
- Parallel paths for alternative fallback chains
- Recursive oversight for self-validating feedback loops
- Backward compatible with v2.0.0

**Reference:** See [WOLFIE Headers documentation](https://github.com/lupopedia/WOLFIE_HEADERS) for complete v2.0.1 details.

---

© 2025 Eric Robin Gerdes / LUPOPEDIA LLC. All rights reserved. Source code will be released under the LUPOPEDIA licensing model (GPL v3.0 + Apache 2.0) upon reaching v1.0.0. Until then, no code is available in this repository.

