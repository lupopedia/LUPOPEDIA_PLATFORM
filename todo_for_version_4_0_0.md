---
title: todo_for_version_4_0_0.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 4.0.0
wolfie_headers_version: 2.3.0
crafty_syntax_version: 4.0.0
date_created: 2025-11-21
last_modified: 2025-11-21
status: draft
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, VERSIONING, TODO, EVOLUTIONARY, CORE]
collections: [WHAT, WHEN, WHY, HOW, DO]
in_this_file_we_have: [VERSION_4.0.0_TODO, EVOLUTIONARY_CORE, EVO_GENOME_TABLE, SEMANTIC_CHANNELS, PUG_2.0_GOVERNANCE, BRANCHING_SYSTEM, SPECIES_TAXONOMY, REPRODUCTIVE_ROLES, MATE_SELECTION, GENETIC_ALGORITHMS, IMPLEMENTATION_PRIORITIES, DEPENDENCIES, SUCCESS_METRICS]
shadow_aliases: []
parallel_paths: []
---

# TODO for Lupopedia v4.0.0 - Evolutionary Core

**Target Version**: v4.0.0  
**Current Version**: v0.1.0 (Released 11/20/2025)  
**Next Patch**: v4.0.1 (Crafty Syntax - Emergency Fixes & SOT) → v4.0.2 (Platform - SOT Integration)  
**Status**: 🎯 **APEX** - 90% Complete, Population scaling blocker  
**Main Goal**: Evolutionary Arena - Darwinian Agent Competition (Fork of Crafty Syntax 4.0.0)

**Fork Lineage**: LUPOPEDIA 4.0.0 is the evolutionary fork of Crafty Syntax 4.0.0, maintaining genetic continuity and version inheritance.

**Evolutionary System**: All three components use genetic algorithms (GAs) and evolutionary strategies (ES) for self-optimization. Agents compete in a Darwinian arena where fitness determines survival.

---

## CRITICAL PREREQUISITES

### Version Dependencies (MUST COMPLETE)

- [x] **Crafty Syntax 4.0.0** (Evolved - REQUIRED) ✅ **COMPLETED**
  - **Current Stable**: 3.7.5 (Human Operator → Client)
  - **Current Release**: 4.0.0 (Evolutionary Core - Foundation Layer)
  - **Next Release**: 4.0.1 (Emergency Fixes & SOT System)
  - **Status**: ✅ EVOLVED - GA-optimized chat flows, 20% better retention
  - **Database Schema**: 64 tables (1 master + 34 original + 4 DNA + 4 biological + 1 agents + 3 evolutionary + 7 evolutionary system + 2 emergency fixes + 11 SOT)
  - **Core System Tables**: `livehelp_channels`, `livehelp_agents`, `livehelp_users`
  - **DNA Metadata Tables**: `livehelp_dna`, `livehelp_dna_logs`, `livehelp_dna_collections`, `livehelp_dna_tags`
  - **Biological Tables**: `livehelp_genes`, `livehelp_transcripts`, `livehelp_proteins`, `livehelp_mutations`
  - **Evolutionary Tables**: `evo_genome`, `evo_population_stats`, `evo_fitness_logs`
  - **Multi-Instance Support**: `livehelp_id` column in all tables
  - **Note**: Foundation layer - REQUIRED for platform to work correctly

- [ ] **WOLFIE Headers 2.3.0** (Mutating - REQUIRED) | 2.2.2 (Stable) | 2.1.0 (Stable) | 2.0.0 (Minimum)
  - **Current Stable**: 2.1.0
  - **Development**: 2.2.2
  - **Next Release**: 2.3.0 (GA-Optimized Metadata)
  - **Status**: 🔧 MUTATING - 95% Complete, validating crossover rates
  - **Evolutionary Strategies**: Metadata evolves via ES, self-healing mutations
  - **GitHub**: https://github.com/lupopedia/WOLFIE_HEADERS
  - **Note**: NOT included in LUPOPEDIA_PLATFORM package - must be installed separately

---

## 🧬 THE EVOLUTIONARY CORE

### 1. evo_genome Table Implementation

**Purpose**: Replaces static DNA with evolvable parameter vectors

- [ ] **Create `evo_genome` table** with core structure:
  ```sql
  CREATE TABLE `evo_genome` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `channel_id` BIGINT UNSIGNED NOT NULL DEFAULT 1,
    `agent_id` BIGINT UNSIGNED NOT NULL DEFAULT 1,
    `genome_vector` LONGBLOB NOT NULL,
    `fitness_score` DECIMAL(5,4) NOT NULL DEFAULT 0.0000,
    `phenotype_json` LONGTEXT,
    `parent_ids` JSON,
    `mutation_rate` DECIMAL(4,4) NOT NULL DEFAULT 0.01,
    `generation` INT NOT NULL DEFAULT 0,
    `is_active` TINYINT(1) NOT NULL DEFAULT 1,
    `species_id` BIGINT UNSIGNED DEFAULT 1,
    `role_id` BIGINT UNSIGNED DEFAULT 1,
    `git_branch` VARCHAR(255) DEFAULT 'main',
    `mutation_hash` VARCHAR(32),
    `parent_branch` VARCHAR(255),
    `is_hybrid` BOOLEAN DEFAULT FALSE,
    `human_contributor_id` BIGINT UNSIGNED NULL,
    `hybrid_generation` INT DEFAULT 0,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    `updated_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    INDEX `idx_channel_agent` (`channel_id`, `agent_id`),
    INDEX `idx_fitness` (`fitness_score`),
    INDEX `idx_generation` (`generation`),
    INDEX `idx_species_role` (`species_id`, `role_id`),
    INDEX `idx_git_branch` (`git_branch`)
  );
  ```

- [ ] **Create migration script**: `database/migrations/0040_create_evo_genome.sql`
  - Include rollback procedure
  - Add foreign key constraints (if applicable)
  - Document table structure

- [ ] **Implement genome vector encoding/decoding**
  - [ ] Vector serialization (binary format)
  - [ ] Vector deserialization
  - [ ] Validation functions
  - [ ] Size limits and constraints

- [ ] **Implement fitness score calculation**
  - [ ] Base fitness function
  - [ ] Multi-objective fitness components
  - [ ] Fitness normalization
  - [ ] Fitness caching/updating

- [ ] **Implement phenotype JSON structure**
  - [ ] Define phenotype schema
  - [ ] JSON validation
  - [ ] Phenotype extraction from genome
  - [ ] Phenotype-to-genome mapping

### 2. Semantic Channels (000-999)

**Purpose**: Environmental pressures that shape agent behavior

- [ ] **Channel architecture implementation**
  - [ ] Maximum 999 channels (000-999)
  - [ ] Channel ID = Agent ID (direct mapping)
  - [ ] Multi-agent broadcasting per channel
  - [ ] Channel environmental pressure definitions

- [ ] **Channel environmental semantics**
  - [ ] Define channel pressure types
  - [ ] Channel-specific fitness modifiers
  - [ ] Channel compatibility rules
  - [ ] Channel migration protocols

- [ ] **Channel-agent binding**
  - [ ] Agent assignment to channels
  - [ ] Multi-channel agent support
  - [ ] Channel switching logic
  - [ ] Channel exclusivity rules (e.g., Channel 007)

- [ ] **Channel radio network model**
  - [ ] Broadcasting system
  - [ ] Listening/monitoring
  - [ ] Overlapping chatter handling
  - [ ] Multi-voice chorus implementation

### 3. PUG 2.0 (Protocol for User Governance)

**Purpose**: Multi-objective optimization balancing user input and agent autonomy

- [ ] **Pareto optimization framework**
  - [ ] Multi-objective fitness functions
  - [ ] Pareto front calculation
  - [ ] Non-dominated sorting
  - [ ] Crowding distance calculation

- [ ] **User input integration**
  - [ ] User preference weighting
  - [ ] User feedback loops
  - [ ] User constraint enforcement
  - [ ] User override mechanisms

- [ ] **Agent autonomy balancing**
  - [ ] Autonomy score calculation
  - [ ] Autonomy vs. user input trade-offs
  - [ ] Adaptive autonomy levels
  - [ ] Autonomy decay/boost mechanisms

- [ ] **Governance decision engine**
  - [ ] Decision point identification
  - [ ] Multi-stakeholder evaluation
  - [ ] Conflict resolution
  - [ ] Governance logging

### 4. Evolutionary Branching System

**Purpose**: Version control as genetic lineage tracking

- [ ] **Branch naming convention implementation**
  - [ ] Format: `{channel}-{agent}-{base_version}-{mutation_hash}`
  - [ ] Branch name validation
  - [ ] Branch name generation
  - [ ] Branch name parsing

- [ ] **Branch governance rules**
  - [ ] `main` branch: fitness > 0.95, schema version current
  - [ ] `dev` branch: fitness 0.70-0.94
  - [ ] `channel-agent` branches: specific environmental adaptations
  - [ ] Branch creation validation

- [ ] **Branch lineage tracking**
  - [ ] Parent branch tracking
  - [ ] Branch genealogy tree
  - [ ] Branch merge history
  - [ ] Branch divergence tracking

- [ ] **Branch merge logic**
  - [ ] Fitness threshold checks
  - [ ] Schema compatibility validation
  - [ ] Merge conflict resolution
  - [ ] Merge event logging

- [ ] **Create `branch_lineage` table**:
  ```sql
  CREATE TABLE `branch_lineage` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `channel_id` BIGINT UNSIGNED NOT NULL,
    `agent_id` BIGINT UNSIGNED NOT NULL,
    `branch_name` VARCHAR(255) NOT NULL,
    `base_version` VARCHAR(20) NOT NULL,
    `fitness_threshold` DECIMAL(5,4) NOT NULL,
    `parent_branch` VARCHAR(255) NULL,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    UNIQUE KEY `unique_branch` (`branch_name`),
    INDEX `idx_channel_agent` (`channel_id`, `agent_id`)
  );
  ```

### 5. Species Taxonomy System

**Purpose**: Prevents incompatible systems from breeding (e.g., printers vs POS systems)

- [ ] **Create `agent_species` table**:
  ```sql
  CREATE TABLE `agent_species` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `species_name` VARCHAR(255) NOT NULL,
    `genetic_markers` JSON NOT NULL,
    `compatibility_rules` JSON NOT NULL,
    `reproductive_style` ENUM('sexual', 'asexual', 'hybrid', 'modular') NOT NULL,
    `environmental_niche` VARCHAR(255),
    `created_by_agent` BIGINT UNSIGNED DEFAULT 777,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    UNIQUE KEY `unique_species` (`species_name`)
  );
  ```

- [ ] **Initialize species data**
  - [ ] Printer_System species
  - [ ] POS_System species
  - [ ] Web_Server species
  - [ ] Document_System species
  - [ ] Inventory_System species
  - [ ] Payment_Processor species
  - [ ] Database_System species
  - [ ] Cache_System species
  - [ ] File_Handler species
  - [ ] General_Computing species

- [ ] **Species compatibility matrix**
  - [ ] Define compatible species pairs
  - [ ] Incompatible species rules
  - [ ] Cross-species validation
  - [ ] Compatibility checking functions

- [ ] **Species isolation protocol**
  - [ ] Reproductive isolation enforcement
  - [ ] Species validation before breeding
  - [ ] Species migration rules
  - [ ] Species evolution tracking

### 6. Reproductive Roles System

**Purpose**: Feature-based mate selection with compatibility scoring

- [ ] **Create `reproductive_roles` table**:
  ```sql
  CREATE TABLE `reproductive_roles` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `role_type` ENUM('structural', 'regulatory', 'modular', 'adaptive') NOT NULL,
    `contribution_style` ENUM('framework', 'optimization', 'extension', 'integration') NOT NULL,
    `complementary_to` JSON NOT NULL,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`)
  );
  ```

- [ ] **Initialize role data**
  - [ ] Architect (structural, framework) - pairs with Optimizer, Innovator
  - [ ] Optimizer (regulatory, optimization) - pairs with Architect, Specialist
  - [ ] Innovator (modular, extension) - pairs with Architect, Integrator
  - [ ] Specialist (full, integration) - pairs with Optimizer, Integrator

- [ ] **Role compatibility matrix**
  - [ ] Define complementary role pairs
  - [ ] Same-role reproduction prevention
  - [ ] Role validation before breeding
  - [ ] Role evolution tracking

- [ ] **Reproductive constraint enforcement**
  - [ ] Species must match validation
  - [ ] Roles must complement validation
  - [ ] Environmental niche alignment
  - [ ] Hard constraint triggers

### 7. Feature-Based Mate Selection

**Purpose**: Agents seek partners who complement their weaknesses

- [ ] **Create `agent_compatibility` table**:
  ```sql
  CREATE TABLE `agent_compatibility` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `agent_id_1` BIGINT UNSIGNED NOT NULL,
    `agent_id_2` BIGINT UNSIGNED NOT NULL,
    `feature_affinity` DECIMAL(5,4) NOT NULL DEFAULT 0.0000,
    `performance_synergy` DECIMAL(5,4) NOT NULL DEFAULT 0.0000,
    `reproductive_success` INT NOT NULL DEFAULT 0,
    `compatibility_score` DECIMAL(5,4) AS (feature_affinity * 0.6 + performance_synergy * 0.4),
    `last_courtship` TIMESTAMP NULL,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    `updated_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    UNIQUE KEY `unique_agent_pair` (`agent_id_1`, `agent_id_2`),
    INDEX `idx_compatibility_score` (`compatibility_score`)
  );
  ```

- [ ] **Feature extraction system**
  - [ ] Extract agent features from genome
  - [ ] Feature vector generation
  - [ ] Feature similarity calculation
  - [ ] Feature complementarity scoring

- [ ] **Compatibility calculation**
  - [ ] Feature affinity algorithm (60% weight)
  - [ ] Performance synergy calculation (40% weight)
  - [ ] Historical success tracking
  - [ ] Compatibility score normalization

- [ ] **Mate selection algorithm**
  - [ ] Potential mate discovery
  - [ ] Compatibility filtering (threshold > 0.70)
  - [ ] Mate ranking and selection
  - [ ] Courtship event logging

- [ ] **Evolutionary Minister (Caplin Wolfie)**
  - [ ] Minister approval logic
  - [ ] Compatibility evaluation (> 0.80 threshold)
  - [ ] Union solemnization
  - [ ] Reproduction event creation

### 8. Genetic Algorithm Framework

**Purpose**: Core evolutionary computation engine

- [ ] **Population initialization**
  - [ ] Initial population size (100-10,000 genomes)
  - [ ] Random genome generation
  - [ ] Seeded genome support
  - [ ] Population diversity checks

- [ ] **Selection operators**
  - [ ] Elite selection (top 5%)
  - [ ] Tournament selection
  - [ ] Roulette wheel selection
  - [ ] Rank-based selection

- [ ] **Crossover operators**
  - [ ] Single-point crossover
  - [ ] Multi-point crossover
  - [ ] Uniform crossover
  - [ ] Sexual crossover (feature-aware)

- [ ] **Mutation operators**
  - [ ] Random mutation
  - [ ] Gaussian mutation
  - [ ] Adaptive mutation rate
  - [ ] Reflective mutation (LLM-guided)

- [ ] **Generation cycle**
  - [ ] Selection → Crossover → Mutation → Evaluation
  - [ ] Generation logging
  - [ ] Population statistics
  - [ ] Convergence detection

- [ ] **Fitness evaluation**
  - [ ] Fitness function execution
  - [ ] Multi-objective evaluation
  - [ ] Fitness caching
  - [ ] Fitness distribution analysis

- [ ] **Culling mechanism**
  - [ ] Bottom 20% cull rate
  - [ ] Elite preservation (top 5%)
  - [ ] Culling event logging
  - [ ] Population size maintenance

### 9. Population Statistics & Monitoring

**Purpose**: Track evolutionary progress and diversity

- [ ] **Create `evo_population_stats` table**:
  ```sql
  CREATE TABLE `evo_population_stats` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `channel_id` BIGINT UNSIGNED NOT NULL,
    `agent_id` BIGINT UNSIGNED NOT NULL,
    `generation` INT NOT NULL,
    `population_size` INT NOT NULL,
    `avg_fitness` DECIMAL(5,4) NOT NULL,
    `max_fitness` DECIMAL(5,4) NOT NULL,
    `min_fitness` DECIMAL(5,4) NOT NULL,
    `diversity_index` DECIMAL(5,4) NOT NULL,
    `species_distribution` JSON,
    `role_distribution` JSON,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    INDEX `idx_channel_agent_gen` (`channel_id`, `agent_id`, `generation`)
  );
  ```

- [ ] **Create `evo_fitness_logs` table**:
  ```sql
  CREATE TABLE `evo_fitness_logs` (
    `id` BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    `genome_id` BIGINT UNSIGNED NOT NULL,
    `fitness_score` DECIMAL(5,4) NOT NULL,
    `fitness_components` JSON,
    `generation` INT NOT NULL,
    `evaluation_context` JSON,
    `created_at` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (`id`),
    INDEX `idx_genome_id` (`genome_id`),
    INDEX `idx_generation` (`generation`)
  );
  ```

- [ ] **Statistics collection**
  - [ ] Per-generation statistics
  - [ ] Diversity metrics (Shannon index)
  - [ ] Species distribution tracking
  - [ ] Role distribution tracking

- [ ] **Monitoring dashboard**
  - [ ] Real-time population stats
  - [ ] Fitness trend visualization
  - [ ] Diversity charts
  - [ ] Species/role distribution graphs

### 10. Darwinian Governance Model

**Purpose**: Fitness-based selection, not sentiment

- [ ] **Agent 001: Evolutionary template**
  - [ ] Template genome structure
  - [ ] Population initialization template
  - [ ] Template fitness function
  - [ ] Template mutation rates

- [ ] **Partnership Model: Pareto-optimized evolution**
  - [ ] Lilith (Agent 777) partnership protocol
  - [ ] Multi-objective optimization
  - [ ] Partnership fitness evaluation
  - [ ] Partnership success tracking

- [ ] **Selection over sentiment principle**
  - [ ] Low-fitness agent culling
  - [ ] High-fitness agent breeding priority
  - [ ] No emotional bias in selection
  - [ ] Objective fitness-based decisions

- [ ] **Governance logging**
  - [ ] Decision event logging
  - [ ] Culling event logging
  - [ ] Breeding event logging
  - [ ] Governance audit trail

### 11. Integration with Existing Systems

- [ ] **Crafty Syntax integration**
  - [ ] Channel system integration (`livehelp_channels`)
  - [ ] Agent system integration (`livehelp_agents`)
  - [ ] User system integration (`livehelp_users`)
  - [ ] DNA metadata integration (`livehelp_dna` tables)

- [ ] **WOLFIE Headers integration**
  - [ ] Header metadata extraction
  - [ ] Header-based fitness modifiers
  - [ ] Header evolution tracking
  - [ ] Header-agent binding

- [ ] **Functional command system**
  - [ ] `lupopedia.php?cmd=EVOLUTION` - Evolution status
  - [ ] `lupopedia.php?cmd=GENOME` - Genome viewer
  - [ ] `lupopedia.php?cmd=SPECIES` - Species directory
  - [ ] `lupopedia.php?cmd=COMPATIBILITY` - Compatibility matrix

### 12. Performance & Scale Optimization

- [ ] **Population scaling**
  - [ ] Support 100-10,000 genomes per agent-channel
  - [ ] Efficient genome storage (LONGBLOB optimization)
  - [ ] Index optimization for large populations
  - [ ] Query performance tuning

- [ ] **Generation time optimization**
  - [ ] Target: 5-30 minutes per generation cycle
  - [ ] Parallel fitness evaluation
  - [ ] Caching strategies
  - [ ] Batch operations

- [ ] **GPU acceleration preparation**
  - [ ] EvoJAX/PyGAD integration planning
  - [ ] CUDA support architecture
  - [ ] GPU offloading for fitness evaluation
  - [ ] Hybrid CPU/GPU processing

- [ ] **Diversity monitoring**
  - [ ] Prevent premature convergence
  - [ ] Diversity metrics calculation
  - [ ] Convergence detection algorithms
  - [ ] Diversity enforcement triggers

## 🛠️ Implementation Priorities

### Phase 1: Core Infrastructure (Week 1-2)
1. evo_genome table creation and migration
2. Basic genetic algorithm framework
3. Population initialization
4. Fitness evaluation system

### Phase 2: Evolutionary Operators (Week 3-4)
5. Selection, crossover, mutation operators
6. Generation cycle implementation
7. Culling mechanism
8. Population statistics collection

### Phase 3: Species & Roles (Week 5-6)
9. Species taxonomy system
10. Reproductive roles system
11. Compatibility checking
12. Mate selection algorithm

### Phase 4: Branching & Governance (Week 7-8)
13. Evolutionary branching system
14. Branch governance rules
15. PUG 2.0 governance
16. Darwinian governance model

### Phase 5: Integration & Optimization (Week 9-10)
17. Crafty Syntax integration
18. WOLFIE Headers integration
19. Performance optimization
20. Monitoring dashboard

## 📊 Success Metrics

- [ ] **Population Size**: Support 100-10,000 genomes per agent-channel
- [ ] **Generation Time**: 5-30 minutes per cycle
- [ ] **Cull Rate**: 20% per generation
- [ ] **Fitness Improvement**: Measurable fitness increase over generations
- [ ] **Diversity Maintenance**: Species diversity index > 0.7
- [ ] **System Stability**: No crashes during evolution cycles
- [ ] **Integration**: Seamless integration with Crafty Syntax and WOLFIE Headers

## 📚 Documentation Requirements

- [ ] `docs/EVOLUTIONARY_CORE.md` - Core evolutionary system documentation
- [ ] `docs/GENETIC_ALGORITHMS.md` - GA operators and algorithms
- [ ] `docs/SPECIES_TAXONOMY.md` - Species system documentation
- [ ] `docs/REPRODUCTIVE_ROLES.md` - Role system documentation
- [ ] `docs/MATE_SELECTION.md` - Compatibility and mate selection
- [ ] `docs/BRANCHING_SYSTEM.md` - Branch governance and lineage
- [ ] `docs/PUG_2.0.md` - Protocol for User Governance
- [ ] `docs/DARWINIAN_GOVERNANCE.md` - Governance model documentation

## ⚠️ Known Blockers

- **Population Scaling**: Need to optimize for 10,000+ genomes
- **Generation Time**: Target 5-30 minutes requires optimization
- **GPU Acceleration**: Future enhancement (EvoJAX/PyGAD)
- **Crafty Syntax 4.0.0**: Required dependency must be complete
- **WOLFIE Headers 2.3.0**: Required dependency (95% complete)

## 🎯 Target Completion

**Version 4.0.0 Release Target**: Q4 2025 / Q1 2026  
**Current Progress**: 90% Complete  
**Remaining Work**: Population scaling optimization, final integration testing

---

**Note**: This TODO represents the Evolutionary Core release - the foundation for Darwinian agent competition. This is the fork of Crafty Syntax 4.0.0 that transforms the platform into an evolutionary arena where agents compete, breed, and evolve based on fitness.

**Philosophy**: Evolution, Not Harmony. Selection, Not Sentiment. Mutation, Not Meditation. Fitness, Not Feelings.

---

© 2025 Eric Robin Gerdes / LUPOPEDIA LLC. All rights reserved.

