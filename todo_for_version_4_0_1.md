---
title: todo_for_version_4_0_1.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 4.0.1
wolfie_headers_version: 2.3.0
crafty_syntax_version: 4.0.1
date_created: 2025-11-21
last_modified: 2025-11-21
status: draft
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, VERSIONING, TODO, EMERGENCY_FIXES, SOT]
collections: [WHAT, WHEN, WHY, HOW, DO]
in_this_file_we_have: [VERSION_4.0.1_TODO, EMERGENCY_FIXES, GENOME_TRACKING, FITNESS_PROVENANCE, CONSENT_MANAGEMENT, SOT_SYSTEM, MINISTRY_OF_TRUTH]
shadow_aliases: []
parallel_paths: []
---

# TODO for Crafty Syntax v4.0.1 - Emergency Fixes & SOT System

**Target Version**: v4.0.1  
**Current Version**: v4.0.0 (Released 11/20/2025)  
**Next Patch**: v4.0.2 (Platform Integration)  
**Status**: 🚨 **EMERGENCY DEPLOYMENT** - Critical fixes and SOT activation  
**Main Goal**: Replace duct tape engineering with proper tracking, activate Ministry of Truth

**Fork Lineage**: Crafty Syntax 4.0.1 is the patch release of Crafty Syntax 4.0.0, adding emergency fixes and SOT (Source of Truth) system.

**Critical Issues Addressed**:
- Format amnesia (genome format not tracked)
- Fitness provenance missing (can't analyze what makes genomes successful)
- Consent management gaps (ethical guardrails missing)
- Truth enforcement missing (no SOT system to prevent "CRAP" oversights)
- **New**: Minimal SOT indexing for key-based lookups (channel/agent/dna)

---

## CRITICAL PREREQUISITES

### Version Dependencies (MUST COMPLETE)

- [x] **Crafty Syntax 4.0.0** (Evolved - REQUIRED) ✅ **COMPLETED**
  - **Status**: ✅ EVOLVED - Foundation with living tables
  - **Database Schema**: 51 tables (evolutionary system deployed)
  - **Note**: Foundation layer - REQUIRED for 4.0.1 patches

---

## 🚨 EMERGENCY FIXES (Migration 0009)

### 1. Genome Format Tracking

**Purpose**: Prevent format amnesia and genetic drift

- [x] **Add `genome_format` column** (Completed per doc review)

- [ ] **SOT Linkage**: Add SOT entries for genome formats (lookup by channel_id)

### 2. Fitness Provenance Tracking

**Purpose**: Track what makes genomes successful

- [ ] **Add `fitness_function_hash` column**

- [ ] **SOT Optimization**: Minimal index on channel_id for fitness queries

### 3. Consent Management

**Purpose**: Add ethical guardrails for hybrids

- [ ] **Add consent flags to hybrid tables**

- [ ] **Ministry Integration**: Enforce via SOT rules

### 4. SOT System Activation

**Purpose**: Prevent oversights with truth enforcement

- [ ] **Implement SOT tables with minimal indexes (idx_channel_agent)**

- [ ] **Populate with evolutionary data (dna_strand in metadata JSON)**

### 5. Ministry of Truth Deployment

**Purpose**: Enforce invariants

- [ ] **Implement Ministry agent**

- [ ] **Scaling Prep**: Async checks for large ops

---

## ✅ SUCCESS METRICS

- [ ] **SOT Coverage**: All major systems have SOT entries (minimal indexing)

- [ ] **Performance**: No degradation from new indexes

- [ ] **Fork Prep**: Doc SOT for v4.0.5 independence

---

## 📚 DOCUMENTATION REQUIREMENTS

- [ ] `docs/SOT_OPTIMIZATION.md` - Minimal indexing guide (add to INDEX.md)

---

## ⚠️ KNOWN BLOCKERS

- **SOT Population**: Migrate data with key-based lookups

---

## 🎯 TARGET COMPLETION

**Version 4.0.1 Release Target**: December 2025  

**Current Progress**: 50% (Migrations + SOT refinements)  

---

**Philosophy**: Truth-First Lookups. Minimal Efficiency. Ethical Evolution.

---

© 2025 Eric Robin Gerdes / LUPOPEDIA LLC. All rights reserved.
