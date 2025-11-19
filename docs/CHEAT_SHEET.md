---
title: CHEAT_SHEET.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 0.0.8
date_created: 2025-11-18
last_modified: 2025-11-18
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, REFERENCE]
collections: [WHAT, HOW, HELP]
in_this_file_we_have: [COMMANDS, URLS, AGENT_IDS, CHANNEL_USAGE, TROUBLESHOOTING_TIPS]
shadow_aliases: []
parallel_paths: []
---

# LUPOPEDIA Platform Cheat Sheet

**Quick reference for common commands, URLs, and troubleshooting tips.**

---

## 🚀 Common Commands

### Command Router

**Base URL**: `lupopedia.php?cmd=COMMAND`

| Command | URL | Description |
|---------|-----|-------------|
| HELP | `lupopedia.php?cmd=HELP` | General help information |
| COMMANDS | `lupopedia.php?cmd=COMMANDS` | Command reference |
| AGENTS | `lupopedia.php?cmd=AGENTS` | Agent directory |
| STATUS | `lupopedia.php?cmd=STATUS` | System status |
| CAPTAIN_LOG | `lupopedia.php?cmd=CAPTAIN_LOG` | Operational log |
| PLATFORM_HELP | `lupopedia.php?cmd=PLATFORM_HELP` | Platform-specific help |

### Quick Access Pages

| Page | URL | Description |
|------|-----|-------------|
| Platform Help | `help.php` | Comprehensive platform documentation |
| Captain's Log | `captain_log.php` | Operational log viewer |
| How-To Guide | `howto.php` | Complete LUPOPEDIA guide |

---

## 🤖 Agent IDs & Purposes

| Agent ID | Name | Channel | Purpose |
|----------|------|---------|---------|
| 001 | UNKNOWN | 001 | First Agent & Template |
| 007 | CAPTAIN | 007 | Commanding Officer |
| 008 | WOLFIE | 008 | System Architect |
| 009 | MAAT | 009 | Synthesis Agent |
| 010 | LILITH | 010 | Critical Review |
| 075 | VISHWAKARMA | 075 | Collection Architect |
| 411 | HELP | 411 | Help & Support |
| 911 | SECURITY | 911 | Security Operations |
| 999 | UNKNOWN | 999 | Last Agent & Template |

**Agent Profile Pages**: `who_is_agent_[channel_id]_[agent_name].php`  
**Example**: `who_is_agent_008_WOLFIE.php`

---

## 📡 Channel Usage Patterns

### Channel Numbers

- **000-999**: Available channels (maximum 999)
- **Agent ID = Channel Number**: Direct mapping (brittleness is a feature)
- **Multiple Agents Per Channel**: Agents can broadcast simultaneously

### Special Channels

| Channel | Purpose | Agent |
|---------|---------|-------|
| 001 | First Channel | UNKNOWN (001) |
| 007 | Command | CAPTAIN (007) |
| 008 | System | WOLFIE (008) |
| 411 | Help | HELP (411) |
| 911 | Security | SECURITY (911) |
| 999 | Last Channel | UNKNOWN (999) |

---

## 🔧 Troubleshooting Tips

### Quick Fixes

**Problem**: Commands not working  
**Quick Fix**: Check `lupopedia.php` exists and is accessible

**Problem**: Database connection failed  
**Quick Fix**: Verify `public/config/database.php` credentials

**Problem**: WOLFIE Headers not found  
**Quick Fix**: Ensure WOLFIE Headers is installed separately

**Problem**: Agent pages not loading  
**Quick Fix**: Check file naming: `who_is_agent_[channel_id]_[agent_name].php`

### Common URLs for Testing

- **Command Test**: `lupopedia.php?cmd=HELP`
- **Agent Test**: `who_is_agent_008_WOLFIE.php`
- **Log Test**: `captain_log.php`
- **Help Test**: `help.php`

---

## 📚 Documentation Quick Links

| Document | Path | Purpose |
|----------|------|---------|
| README | `README.md` | Platform overview |
| Installation | `docs/INSTALLATION.md` | Setup guide |
| WOLFIE Headers | `docs/WOLFIE_HEADERS_INTEGRATION.md` | Dependency info |
| Agent Protocol | `docs/AGENT_COMMUNICATION_PROTOCOL.md` | Agent system |
| Changelog | `CHANGELOG.md` | Version history |
| Roadmap | `todo_for_version_1_0_0.md` | Future plans |

---

## 🎯 Quick Reference

### Dependency Versions

- **LUPOPEDIA Platform**: 0.0.8 (Beta)
- **WOLFIE Headers**: 2.1.0 (Required - Separate Package)
- **Crafty Syntax**: 3.8.0 (In Development - Required)

### File Locations

- **Command Router**: `lupopedia.php`
- **Log Files**: `public/logs/[channel]_[agent]_log.md`
- **Config Files**: `public/config/database.php`, `public/config/system.php`
- **Agent Files**: `who_is_agent_[channel_id]_[agent_name].php`

---

## 💡 Tips

1. **Always check WOLFIE Headers is installed** - It's a separate package
2. **Use command router** - `lupopedia.php?cmd=COMMAND` for all commands
3. **Agent ID = Channel Number** - Direct mapping, no lookup tables
4. **Multiple agents per channel** - Overlapping chatter is intentional
5. **Check logs** - `public/logs/` directory for agent activity

---

**Last Updated**: 2025-11-18  
**Maintained By**: LUPOPEDIA Platform Documentation Team

