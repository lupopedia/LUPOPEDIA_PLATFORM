---
title: README.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 0.0.8
wolfie_headers_version: 2.2.2
crafty_syntax_version: 3.8.0
date_created: 2025-11-09
last_modified: 2025-11-18
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION]
collections: [WHAT, WHY, HOW, HELP]
in_this_file_we_have: [OVERVIEW, CURRENT_STATUS, FUNCTIONAL_COMMANDS, AGENT_SYSTEM, CHANNEL_SYSTEM, HOW_TO_REQUEST_ACCESS, ROADMAP, QUICK_START, STATUS_TABLE]
shadow_aliases: []
parallel_paths: []
---

# LUPOPEDIA Platform

**Version**: v0.0.8 (Functional Command System)  
**Status**: Building While Flying  
**License**: GPL v3.0 + Apache 2.0 (dual license)  
**Copyright**: © 2025 LUPOPEDIA LLC

## Quick Navigation

- [Current Status](#current-status)
- [Quick Start](#-quick-start)
- [What's Working Now](#-whats-working-now)
- [What's Next](#-whats-next)
- [Getting Started](docs/INDEX.md)
- [Installation Guide](docs/INSTALLATION.md)
- [Agent System](docs/AGENT_COMMUNICATION_PROTOCOL.md)
- [WOLFIE Headers Integration](docs/WOLFIE_HEADERS_INTEGRATION.md)
- [Changelog](CHANGELOG.md)
- [Roadmap](todo_for_version_1_0_0.md)
- [Cheat Sheet](docs/CHEAT_SHEET.md)

---

## 🚀 Quick Start

1. **Install Crafty Syntax 3.8.0** (prerequisite - in development, Pre-Alpha target: December 2025)
   - **Database Schema**: 37 tables (30 existing + 4 DNA + 3 core system: channels, agents, users)
   - **Core System Tables**: `livehelp_channels`, `livehelp_agents`, `livehelp_users`
   - **DNA Metadata Tables**: `livehelp_A`, `livehelp_C`, `livehelp_G`, `livehelp_T`
2. **Install WOLFIE Headers 2.2.2** (required dependency - separate package, current version)
   - See [WOLFIE Headers Integration Guide](docs/WOLFIE_HEADERS_INTEGRATION.md) for details
3. **Download LUPOPEDIA Platform**
4. **Run setup verification**
   - See [Installation Guide](docs/INSTALLATION.md) for step-by-step instructions

**⚠️ CRITICAL**: WOLFIE Headers is **NOT included** in the LUPOPEDIA_PLATFORM package and must be installed separately.

---

## Current Status (2025-11-18)

| Component | Version | Status | Notes |
|-----------|---------|--------|-------|
| LUPOPEDIA Platform | 0.0.8 | Beta | Functional command system |
| WOLFIE Headers | 2.2.2 | ✅ Released | Required dependency - Advanced search, export, analytics |
| Crafty Syntax | 3.8.0 | ⚠️ In Development | **Critical Blocker** - Pre-Alpha Dec 2025, 37 tables (30+4 DNA+3 core) |

---

## 🎯 What's Working Now

✅ **Functional Command System** - `lupopedia.php` command router operational  
✅ **Agent Profile Pages** - Public profiles for all agents (000-999)  
✅ **Captain's Log Viewer** - Operational log with multi-agent perspectives  
✅ **Comprehensive Help Documentation** - Sitcom-style documentation  
✅ **How-To Guide** - Complete LUPOPEDIA guide  

---

## 🔧 What's Next

🔄 **Channel Radio Network** - 1000-channel architecture (000-999)  
📡 **Multi-Agent Broadcasting** - Overlapping chatter system  
🧬 **Agent DNA System** - Agents creating other agents  
📚 **Agent Creation Workflow** - Factory pattern for agent spawning  

See [Roadmap](todo_for_version_1_0_0.md) for complete details.

---

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
    Version: 3.8.0 (in development) - REQUIRED
    Latest Stable: 3.7.5
    Pre-Alpha Target: December 2025
    Philosophy: "Always works"
    Status: ⚠️ IN DEVELOPMENT - **CRITICAL BLOCKER** - Required for LUPOPEDIA_PLATFORM to work correctly
    Database Schema: 37 tables (30 existing + 4 DNA metadata + 3 core system: channels, agents, users)
    Core System Tables: livehelp_channels, livehelp_agents, livehelp_users
    DNA Metadata Tables: livehelp_A, livehelp_C, livehelp_G, livehelp_T (context-dependent by channel_id + agent_name)
    Multi-Instance Support: livehelp_id column in all 37 tables
    ↓
    └─> WOLFIE Headers System (2025) [Required Dependency - Separate Package]
        Version: 2.2.2 (Current - REQUIRED) | 2.2.0 (Stable) | 2.1.0 (Stable) | 2.0.9 (Stable) | 2.0.8 (Stable) | 2.0.7 (Stable) | 2.0.6 (Stable) | 2.0.5 (Stable) | 2.0.4 (Stable) | 2.0.3 (Stable) | 2.0.2 (Stable) | 2.0.1 (Stable) | 2.0.0 (Minimum) - REQUIRED
        GitHub: https://github.com/lupopedia/WOLFIE_HEADERS
        10-section format (WHO, WHAT, WHERE, WHEN, WHY, HOW, DO, HACK, OTHER, TAGS)
        YAML frontmatter documentation system
        Shadow aliases & parallel paths (v2.0.1)
        Database integration (v2.0.2)
        Log file system (v2.0.3)
        Agent integration (v2.0.4)
        Log reader system (v2.0.5)
        API endpoints & search functionality (v2.0.6)
        Database `_logs` table support (v2.0.7)
        Shared hosting compatibility & self-contained configuration (v2.0.8)
        Three log systems documentation (v2.0.9)
        API consistency, error handling, user onboarding (v2.1.0)
        Enhanced log reader with database integration (v2.2.0)
        Advanced search, export, and analytics (v2.2.2)
        NOT included in LUPOPEDIA_PLATFORM package - must be installed separately
        ↓
        └─> LUPOPEDIA_PLATFORM (2025) [Layer 1]
            Current: 0.0.8 | Target: 1.0.0
            Requires: WOLFIE Headers 2.2.2 (current) | 2.2.0 (stable) | 2.1.0 (stable) | 2.0.9 (stable) | 2.0.8 (stable) | 2.0.7 (stable) | 2.0.6 (stable) | 2.0.5 (stable) | 2.0.4 (stable) | 2.0.3 (stable) | 2.0.2 (stable) | 2.0.1 (stable) | 2.0.0 (minimum)
            Requires: Crafty Syntax 3.8.0 (in development, Pre-Alpha Dec 2025) - **CRITICAL BLOCKER** - REQUIRED
            ↓
            └─> Agent System (2025) [Layer 2]
                Channels: 000-999 (maximum 999)
                Agents can make other agents
                Radio network model
```

**Why This Matters**: Each layer builds on the previous. You cannot skip WOLFIE Headers 2.1.0 or Crafty Syntax 3.8.0 - they are **required dependencies** for LUPOPEDIA_PLATFORM to work correctly. WOLFIE Headers is **NOT included** in the LUPOPEDIA_PLATFORM package and must be installed independently.

**⚠️ CRITICAL REQUIREMENTS**:
- **WOLFIE Headers 2.2.2** (Current - REQUIRED) - See [WOLFIE Headers Integration Guide](docs/WOLFIE_HEADERS_INTEGRATION.md) for complete details
- **Crafty Syntax 3.8.0** (In Development - **CRITICAL BLOCKER**) - Foundation layer, Pre-Alpha target: December 2025
  - **Database Schema**: 37 tables (30 existing + 4 DNA + 3 core system: channels, agents, users)
  - **Core System Tables**: Required for channel management, agent coordination, user management
  - **DNA Metadata Tables**: Context-dependent metadata lookup by `channel_id` and `agent_name`

**📚 For complete WOLFIE Headers information**, see: [WOLFIE Headers Integration Guide](docs/WOLFIE_HEADERS_INTEGRATION.md)

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
   - Crafty Syntax 3.8.0 (Pre-Alpha target: December 2025, **CRITICAL BLOCKER**)
     - 37 tables (30 existing + 4 DNA + 3 core system: channels, agents, users)
     - Core system tables: `livehelp_channels`, `livehelp_agents`, `livehelp_users`
     - DNA metadata tables: `livehelp_A`, `livehelp_C`, `livehelp_G`, `livehelp_T`
   - WOLFIE Headers 2.2.2 (Current - REQUIRED) | 2.2.0 (Stable) | 2.1.0 (Stable) | 2.0.9 (Stable) | 2.0.8 (Stable) | 2.0.7 (Stable) | 2.0.6 (Stable) | 2.0.5 (Stable) | 2.0.4 (Stable) | 2.0.3 (Stable) | 2.0.2 (Stable) | 2.0.1 (Stable) | 2.0.0 (Minimum) - **REQUIRED - separate package, NOT included**
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

## WOLFIE Headers Integration

**📚 For complete WOLFIE Headers version history, features, installation, and integration details**, see: [WOLFIE Headers Integration Guide](docs/WOLFIE_HEADERS_INTEGRATION.md)

This guide includes:
- Complete version history (v2.0.0 through v2.1.0)
- Feature summaries for each version
- Installation instructions
- Integration with LUPOPEDIA Platform
- Reference documentation links

---

## 🆘 Need Help?

- [View Online Documentation](https://github.com/lupopedia/lupopedia_platform/docs)
- [Report Issues](https://github.com/lupopedia/lupopedia_platform/issues)
- [Contact Support](docs/SUPPORT.md)
- [Cheat Sheet](docs/CHEAT_SHEET.md) - Quick reference for commands and URLs

---

© 2025 Eric Robin Gerdes / LUPOPEDIA LLC. All rights reserved. Source code will be released under the LUPOPEDIA licensing model (GPL v3.0 + Apache 2.0) upon reaching v1.0.0. Until then, no code is available in this repository.

