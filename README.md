---
title: README.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 2.0.4
date_created: 2025-11-09
last_modified: 2025-11-18
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION]
collections: [WHAT, WHY, HOW, HELP]
in_this_file_we_have: [OVERVIEW, CURRENT_STATUS, FUNCTIONAL_COMMANDS, AGENT_SYSTEM, CHANNEL_SYSTEM, HOW_TO_REQUEST_ACCESS, ROADMAP, V2.0.2_UPDATE, V2.0.3_UPDATE, V2.0.4_UPDATE]
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
        Version: 2.0.4 (Current) | 2.0.3 (Stable) | 2.0.2 (Stable) | 2.0.1 (Stable) | 2.0.0 (Minimum) - REQUIRED
        GitHub: https://github.com/lupopedia/WOLFIE_HEADERS
        10-section format (WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER, TAGS)
        YAML frontmatter documentation system
        Shadow aliases & parallel paths (v2.0.1)
        Database integration (v2.0.2)
        Log file system (v2.0.3)
        Agent integration (v2.0.4)
        NOT included in LUPOPEDIA_PLATFORM package - must be installed separately
        ↓
        └─> LUPOPEDIA_PLATFORM (2025) [Layer 1]
            Current: 0.0.8 | Target: 1.0.0
            Requires: WOLFIE Headers 2.0.0+ (v2.0.4 recommended, v2.0.3 stable)
            ↓
            └─> Agent System (2025) [Layer 2]
                Channels: 000-999 (maximum 999)
                Agents can make other agents
                Radio network model
```

**Why This Matters**: Each layer builds on the previous. You cannot skip WOLFIE Headers 2.0.0+ - it is a **required, separate dependency** for LUPOPEDIA_PLATFORM. WOLFIE Headers is **NOT included** in the LUPOPEDIA_PLATFORM package and must be installed independently.

**WOLFIE Headers v2.0.4 Features:**
- Agent 007 CAPTAIN integration (v2.0.4) - Commanding Officer
- Agent 001 UNKNOWN integration (v2.0.4) - First Agent & Template
- Agent 999 UNKNOWN integration (v2.0.4) - Last Agent & Template
- Agent repository structure (v2.0.4) - Standardized GitHub repositories
- Log file system with `[channel]_[agent]_log.md` format (v2.0.3)
- `content_log` database table for log metadata (v2.0.3)
- Dual-storage system (database + markdown files) (v2.0.3)
- Database integration with `content_headers` table (`agent_name` column) (v2.0.2)
- Standardized agent file naming convention (`who_is_agent_[channel_id]_[agent_name].php`) (v2.0.2)
- Validation scripts for agent files (v2.0.2)
- Shadow aliases & parallel paths (from v2.0.1)
- Recursive oversight (from v2.0.1)
- Backward compatible with v2.0.3, v2.0.2, v2.0.1, and v2.0.0

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

**The Receptionist Model (Fixed Routing Chain):**

```
User Request
    ↓
WOLFIE (008) - Reads WOLFIE Headers, routes tasks
    ↓
WOLFIE (007) - Tactical operator, transfers to VISH
    ↓
VISHWAKARMA (075) - Normalizes requests, tracks changes
    ↓
Response
```

**Philosophy**: WOLFIE (007) doesn't know what he's doing, but knows who to transfer to (VISH). The system works anyway. Brittleness is a feature.

**📚 For complete protocol documentation**, see: `docs/AGENT_COMMUNICATION_PROTOCOL.md`

## CHANNEL_SYSTEM

Think of LUPOPEDIA as a **radio network on a starship**. Each channel is like a frequency band, and multiple agents can tune in at once.

- **Channels 000-999** available (maximum 999)
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
   - WOLFIE Headers 2.0.4 (Current) | 2.0.3 (Stable) | 2.0.2 (Stable) | 2.0.1 (Stable) | 2.0.0 (Minimum) - **REQUIRED - separate package, NOT included**
   - LUPOPEDIA_PLATFORM 1.0.0 (currently 0.0.8)
2. **Implement channel radio network architecture** (000-999, maximum 999)
   - Phase 1: ✅ Complete (migrations 1075 & 1076, Channel.php updates)
   - Phase 2: ⏳ In progress (Agent ID = Channel Number mapping)
   - See: `docs/CHANNEL_ARCHITECTURE_IMPLEMENTATION_PLAN.md`
3. **Build multi-agent broadcasting system**
   - Protocol: See `docs/AGENT_COMMUNICATION_PROTOCOL.md`
4. **Agent Communication Protocol** (Receptionist Model)
   - ✅ Documentation complete: `docs/AGENT_COMMUNICATION_PROTOCOL.md`
   - ⏳ Implementation: WOLFIE (008) → 007 → VISH (075) routing chain
5. **Enable agent creation workflow** (agents making other agents)

## Philosophy

- **Building While Flying**: Manual written after the engine explodes. But at least the coffee's hot. ☕
- **Brittleness is a Feature**: Agent ID = Channel Number (direct mapping, no lookup tables)
- **Chaos is Intentional**: Overlapping chatter creates sitcom-style logs
- **Sitcom Documentation**: Help files blend technical manual with sitcom script

## V2.0.4_UPDATE

**WOLFIE Headers v2.0.4 Update** (2025-11-18):

LUPOPEDIA_PLATFORM documentation has been updated to reflect WOLFIE Headers v2.0.4 as the current, officially released version. **WOLFIE Headers 2.0.4 is REQUIRED for the platform to work.**

**Release Status**: WOLFIE Headers v2.0.4 has been officially released on GitHub (2025-11-18).
- **Release URL**: https://github.com/lupopedia/WOLFIE_HEADERS
- **Status**: Latest Release (Current)
- **Backward Compatible**: Yes — fully compatible with v2.0.3, v2.0.2, v2.0.1, and v2.0.0

**Key Changes:**
- WOLFIE Headers v2.0.4 (Current) | v2.0.3 (Stable) | v2.0.2 (Stable) | v2.0.1 (Stable) | v2.0.0 (Minimum) - **REQUIRED - separate package, NOT included**
- Agent 007 CAPTAIN integration - Commanding Officer (GitHub: https://github.com/lupopedia/007_captain)
- Agent 001 UNKNOWN integration - First Agent & Template (GitHub: https://github.com/lupopedia/001_unknown)
- Agent 999 UNKNOWN integration - Last Agent & Template (GitHub: https://github.com/lupopedia/999_unknown)
- Agent repository structure - Standardized GitHub repositories
- Agent integration patterns - Documentation for agent repositories
- Log file system features (from v2.0.3) still supported
- Database integration features (from v2.0.2) still supported
- Shadow aliases & parallel paths features (from v2.0.1) still supported
- GitHub link: https://github.com/lupopedia/WOLFIE_HEADERS
- Dependency clarified: WOLFIE Headers must be installed separately

**v2.0.4 New Features:**
- Agent 007 CAPTAIN integration - Commanding Officer & Strategic Coordinator
- Agent 001 UNKNOWN integration - First Agent & Template for new channels
- Agent 999 UNKNOWN integration - Last Agent & Template for new channels
- Agent repository structure - Standardized GitHub repository structure
- Agent integration patterns - Documentation for agent-specific repositories

**v2.0.3 Features (Still Supported):**
- Log file system with `[channel]_[agent]_log.md` format
- `content_log` database table (Migration 1078)
- Dual-storage system (database + markdown files)
- Core functions library (`public/includes/wolfie_log_system.php`)
- Enhanced database sync (smart update-or-insert logic)
- Complete log system documentation

**v2.0.2 Features (Still Supported):**
- Database integration with `content_headers` table
- Standardized agent file naming convention
- Validation scripts for agent files
- Complete database integration documentation

**v2.0.1 Features (Still Supported):**
- Shadow aliases for parallel validation paths (e.g., `["Lilith-007", "Doubt-VISH"]`)
- Parallel paths for alternative fallback chains
- Recursive oversight for self-validating feedback loops
- Backward compatible with v2.0.0

**Reference:** See [WOLFIE Headers documentation](https://github.com/lupopedia/WOLFIE_HEADERS) for complete v2.0.4 details, including:
- `RELEASE_NOTES_v2.0.4.md` - Complete release notes
- `TODO_2.0.4.md` - Complete integration plan
- Agent repositories: https://github.com/lupopedia/007_captain, https://github.com/lupopedia/001_unknown, https://github.com/lupopedia/999_unknown

## V2.0.3_UPDATE

**WOLFIE Headers v2.0.3 Update** (2025-11-18):

LUPOPEDIA_PLATFORM documentation was updated to reflect WOLFIE Headers v2.0.3. **Superseded by v2.0.4** (see above).

**Release Status**: WOLFIE Headers v2.0.3 was officially released on GitHub (2025-11-18).
- **Release URL**: https://github.com/lupopedia/WOLFIE_HEADERS
- **Status**: Stable (Superseded by v2.0.4)
- **Backward Compatible**: Yes — fully compatible with v2.0.2, v2.0.1, and v2.0.0

**Key Changes:**
- WOLFIE Headers v2.0.3 (Stable) | v2.0.2 (Stable) | v2.0.1 (Stable) | v2.0.0 (Minimum) - **REQUIRED - separate package, NOT included**
- Log file system with `[channel]_[agent]_log.md` format
- `content_log` database table for log metadata
- Dual-storage system (database + markdown files)
- Database integration features (`content_headers` table, `agent_name` column) (from v2.0.2)
- Agent file naming convention (`who_is_agent_[channel_id]_[agent_name].php`) (from v2.0.2)
- Shadow aliases & parallel paths features (from v2.0.1) still supported
- GitHub link: https://github.com/lupopedia/WOLFIE_HEADERS
- Dependency clarified: WOLFIE Headers must be installed separately

**v2.0.3 New Features:**
- Log file system with `[channel]_[agent]_log.md` format
- `content_log` database table (Migration 1078)
- Dual-storage system (database + markdown files)
- Core functions library (`public/includes/wolfie_log_system.php`)
- Enhanced database sync (smart update-or-insert logic)
- Complete log system documentation

**v2.0.2 Features (Still Supported):**
- Database integration with `content_headers` table
- Standardized agent file naming convention
- Validation scripts for agent files
- Complete database integration documentation

**v2.0.1 Features (Still Supported):**
- Shadow aliases for parallel validation paths (e.g., `["Lilith-007", "Doubt-VISH"]`)
- Parallel paths for alternative fallback chains
- Recursive oversight for self-validating feedback loops
- Backward compatible with v2.0.0

**Reference:** See [WOLFIE Headers documentation](https://github.com/lupopedia/WOLFIE_HEADERS) for complete v2.0.3 details, including:
- `RELEASE_NOTES_v2.0.3.md` - Complete release notes
- `docs/WOLFIE_HEADERS_LOG_SYSTEM_PLAN.md` - Log system architecture
- `docs/DATABASE_INTEGRATION.md` - Database integration guide (updated with content_log)
- `docs/WOLFIE_HEADER_SYSTEM_OVERVIEW.md` - System overview (updated with LOG_FILE_SYSTEM)
- `docs/LOG_FILE_SYSTEM_EXPLAINED.md` - Comprehensive explanation guide

## V2.0.2_UPDATE

**WOLFIE Headers v2.0.2 Update** (2025-11-17):

LUPOPEDIA_PLATFORM documentation was updated to reflect WOLFIE Headers v2.0.2. **Superseded by v2.0.3** (see above).

**Release Status**: WOLFIE Headers v2.0.2 was officially released on GitHub (2025-11-17).
- **Release URL**: https://github.com/lupopedia/WOLFIE_HEADERS/releases/tag/v2.0.2
- **Status**: Stable (Superseded by v2.0.3)
- **Backward Compatible**: Yes — fully compatible with v2.0.1 and v2.0.0

**v2.0.2 Features:**
- Database integration with `content_headers` table
- Standardized agent file naming convention
- Validation scripts for agent files
- Complete database integration documentation

**Reference:** See [WOLFIE Headers documentation](https://github.com/lupopedia/WOLFIE_HEADERS) for v2.0.2 details.

---

© 2025 Eric Robin Gerdes / LUPOPEDIA LLC. All rights reserved. Source code will be released under the LUPOPEDIA licensing model (GPL v3.0 + Apache 2.0) upon reaching v1.0.0. Until then, no code is available in this repository.

