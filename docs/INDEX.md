---
title: INDEX.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 0.0.8
date_created: 2025-11-18
last_modified: 2025-11-18
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, INDEX]
collections: [WHAT, HOW, HELP]
in_this_file_we_have: [DOCUMENTATION_INDEX, QUICK_START, TROUBLESHOOTING, DEPENDENCY_INSTALLATION]
shadow_aliases: []
parallel_paths: []
---

# LUPOPEDIA Platform Documentation Index

**Welcome to the LUPOPEDIA Platform documentation hub.** This index provides quick navigation to all documentation resources.

---

## 🚀 Quick Start

**New to LUPOPEDIA?** Start here:

1. **[Installation Guide](INSTALLATION.md)** - Step-by-step installation instructions
2. **[WOLFIE Headers Integration](WOLFIE_HEADERS_INTEGRATION.md)** - Required dependency setup
3. **[Cheat Sheet](CHEAT_SHEET.md)** - Quick reference for commands and URLs
4. **[Agent Communication Protocol](AGENT_COMMUNICATION_PROTOCOL.md)** - How agents work together

---

## 📚 Core Documentation

### Getting Started
- **[Installation Guide](INSTALLATION.md)** - Complete installation and setup instructions
- **[WOLFIE Headers Integration](WOLFIE_HEADERS_INTEGRATION.md)** - Single source of truth for WOLFIE Headers
- **[Cheat Sheet](CHEAT_SHEET.md)** - Quick reference for common tasks

### System Architecture
- **[Agent Communication Protocol](AGENT_COMMUNICATION_PROTOCOL.md)** - How agents communicate and route requests
- **[Channel Architecture Implementation Plan](CHANNEL_ARCHITECTURE_IMPLEMENTATION_PLAN.md)** - 1000-channel system design
- **[Evolutionary Branching System](EVOLUTIONARY_BRANCHING_SYSTEM.md)** - Version control as genetic lineage tracking
- **[Platform Status Synthesis](PLATFORM_STATUS_SYNTHESIS.md)** - Current system status

### Reference
- **[Functional Commands Reference](FUNCTIONAL_COMMANDS_REFERENCE.md)** - Complete command documentation
- **[Captain's Log Analysis](CAPTAINS_LOG_ANALYSIS.md)** - Log system overview

---

## 🔧 Troubleshooting

### Common Issues

**Problem**: Cannot connect to database  
**Solution**: Check `public/config/database.php` configuration  
**Related**: [Installation Guide](INSTALLATION.md#database-configuration)

**Problem**: WOLFIE Headers not found  
**Solution**: Ensure WOLFIE Headers is installed separately  
**Related**: [WOLFIE Headers Integration](WOLFIE_HEADERS_INTEGRATION.md#installation)

**Problem**: Commands not working  
**Solution**: Verify `lupopedia.php` is accessible and dependencies are installed  
**Related**: [Functional Commands Reference](FUNCTIONAL_COMMANDS_REFERENCE.md)

**Problem**: Agent pages not loading  
**Solution**: Check agent file naming convention: `who_is_agent_[channel_id]_[agent_name].php`  
**Related**: [Agent Communication Protocol](AGENT_COMMUNICATION_PROTOCOL.md)

### Getting Help

- **[Support Guide](SUPPORT.md)** - How to get help and report issues
- **[Cheat Sheet](CHEAT_SHEET.md)** - Quick troubleshooting tips

---

## 📦 Dependency Installation Sequence

**⚠️ CRITICAL**: Install dependencies in this exact order:

1. **Crafty Syntax 4.0.0** (Foundation - Evolved - **REQUIRED** - Parent Fork)
   - Status: ✅ Evolved - GA-optimized chat flows, 20% better retention
   - **Database Schema**: 44 tables (30 existing + 4 DNA + 4 biological + 3 core + 3 evolutionary)
   - **Core System Tables**: `livehelp_channels`, `livehelp_agents`, `livehelp_users`
   - **DNA Metadata Tables**: `livehelp_dna`, `livehelp_dna_logs`, `livehelp_dna_collections`, `livehelp_dna_tags`
   - **Biological Tables**: `livehelp_genes`, `livehelp_transcripts`, `livehelp_proteins`, `livehelp_mutations`
   - **Evolutionary Tables**: `evo_genome`, `evo_population_stats`, `evo_fitness_logs`
   - **Fork Lineage**: Crafty Syntax 3.7.5 → Crafty Syntax 4.0.0 (parent of LUPOPEDIA fork)
   - See: Crafty Syntax documentation

2. **WOLFIE Headers 2.3.0** (Required Dependency - Separate Package - Mutating)
   - Status: 🔧 Mutating - 95% Complete, validating crossover rates
   - **Features**: Evolutionary strategies, metadata evolution, self-healing mutations
   - See: [WOLFIE Headers Integration Guide](WOLFIE_HEADERS_INTEGRATION.md)
   - **⚠️ NOT included in LUPOPEDIA_PLATFORM package**

3. **LUPOPEDIA Platform 4.0.0** (Current - Apex - Fork of Crafty Syntax 4.0.0)
   - Status: 🎯 Apex - 90% Complete, evolutionary arena operational
   - **Features**: Evolutionary branching system, genetic algorithm integration
   - **Fork Lineage**: LUPOPEDIA 4.0.0 is the evolutionary fork of Crafty Syntax 4.0.0
   - **Version Inheritance**: Maintains genetic continuity by inheriting version number from parent fork
   - See: [Installation Guide](INSTALLATION.md)
   - See: [Evolutionary Branching System](EVOLUTIONARY_BRANCHING_SYSTEM.md)

---

## 🗺️ Navigation

### Main Documentation
- **[README.md](../README.md)** - Platform overview and quick start
- **[CHANGELOG.md](../CHANGELOG.md)** - Version history and updates
- **[Roadmap](../todo_for_version_1_0_0.md)** - Future plans and TODO

### Quick Links
- **[What's Working Now](../README.md#-whats-working-now)** - Current features
- **[What's Next](../README.md#-whats-next)** - Upcoming features
- **[Status Table](../README.md#current-status-2025-11-18)** - Component versions

---

## 📖 Documentation Structure

```
docs/
├── INDEX.md (this file)
├── INSTALLATION.md
├── WOLFIE_HEADERS_INTEGRATION.md
├── EVOLUTIONARY_BRANCHING_SYSTEM.md
├── CHEAT_SHEET.md
├── SUPPORT.md
├── AGENT_COMMUNICATION_PROTOCOL.md
├── CHANNEL_ARCHITECTURE_IMPLEMENTATION_PLAN.md
├── FUNCTIONAL_COMMANDS_REFERENCE.md
├── PLATFORM_STATUS_SYNTHESIS.md
└── CAPTAINS_LOG_ANALYSIS.md
```

---

## 🔍 Finding Information

### By Topic
- **Installation**: [Installation Guide](INSTALLATION.md)
- **Agents**: [Agent Communication Protocol](AGENT_COMMUNICATION_PROTOCOL.md)
- **Channels**: [Channel Architecture](CHANNEL_ARCHITECTURE_IMPLEMENTATION_PLAN.md)
- **Version Control**: [Evolutionary Branching System](EVOLUTIONARY_BRANCHING_SYSTEM.md)
- **Commands**: [Functional Commands Reference](FUNCTIONAL_COMMANDS_REFERENCE.md)
- **WOLFIE Headers**: [WOLFIE Headers Integration](WOLFIE_HEADERS_INTEGRATION.md)

### By Task
- **Setting up**: [Installation Guide](INSTALLATION.md)
- **Using commands**: [Cheat Sheet](CHEAT_SHEET.md)
- **Troubleshooting**: [Support Guide](SUPPORT.md)
- **Understanding system**: [Platform Status Synthesis](PLATFORM_STATUS_SYNTHESIS.md)

---

**Last Updated**: 2025-11-18  
**Maintained By**: LUPOPEDIA Platform Documentation Team

