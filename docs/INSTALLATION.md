---
title: INSTALLATION.md
agent_username: wolfie
agent_id: 008
channel_number: 001
version: 0.0.8
date_created: 2025-11-18
last_modified: 2025-11-18
status: published
onchannel: 1
tags: [SYSTEM, DOCUMENTATION, INSTALLATION]
collections: [WHAT, HOW]
in_this_file_we_have: [INSTALLATION_STEPS, DEPENDENCIES, CONFIGURATION, VERIFICATION]
shadow_aliases: []
parallel_paths: []
---

# LUPOPEDIA Platform Installation Guide

**Step-by-step installation instructions for LUPOPEDIA Platform.**

---

## Prerequisites

Before installing LUPOPEDIA Platform, ensure you have:

- **PHP 7.4+** (or higher)
- **MySQL 5.7+** or **PostgreSQL 10+**
- **Web server** (Apache, Nginx, or similar)
- **Composer** (optional, for dependency management)

---

## Installation Steps

### Step 1: Install Crafty Syntax 3.8.0

**Status**: ⚠️ **IN DEVELOPMENT - CRITICAL BLOCKER** - Pre-Alpha target: December 2025

**⚠️ CRITICAL**: Crafty Syntax 3.8.0 is **REQUIRED** but currently in development. The entire LUPOPEDIA ecosystem is blocked until completion.

**Database Schema Requirements**:
- **37 tables total**: 30 existing + 4 DNA metadata tables + 3 core system tables
- **Core System Tables**: `livehelp_channels`, `livehelp_agents`, `livehelp_users` - Required for channel management, agent coordination, and user management
- **DNA Metadata Tables**: `livehelp_A`, `livehelp_C`, `livehelp_G`, `livehelp_T` - Context-dependent metadata lookup by `channel_id` and `agent_name`
- **Multi-Instance Support**: `livehelp_id` column in all 37 tables for data isolation

**Installation Steps** (when available):
1. Download Crafty Syntax 3.8.0 (Pre-Alpha expected December 2025)
2. Run migration script to create `livehelp` master table and add `livehelp_id` to all 37 tables
3. Create core system tables (channels, agents, users) if they don't exist
4. Follow Crafty Syntax installation instructions
5. Verify installation and multi-instance support

**Note**: Check Crafty Syntax documentation for latest status and interface contracts for LUPOPEDIA developers.

---

### Step 2: Install WOLFIE Headers 2.2.2

**⚠️ CRITICAL**: WOLFIE Headers is **NOT included** in the LUPOPEDIA_PLATFORM package and must be installed separately.

1. **Download WOLFIE Headers**
   - GitHub: https://github.com/lupopedia/WOLFIE_HEADERS
   - Download or clone the repository

2. **Copy Files**
   - Copy the `public/` folder from WOLFIE Headers to your LUPOPEDIA installation
   - Ensure `public/config/`, `public/includes/`, and `public/logs/` directories exist

3. **Configure Database Connection**
   - Edit `public/config/database.php`
   - Update database credentials:
     ```php
     define('WOLFIE_DB_HOST', 'localhost');
     define('WOLFIE_DB_NAME', 'lupopedia');
     define('WOLFIE_DB_USER', 'your_username');
     define('WOLFIE_DB_PASS', 'your_password');
     ```

4. **Configure System Settings**
   - Edit `public/config/system.php`
   - Set `WOLFIE_BORN_YESTERDAY = true` for fresh installations
   - Set `WOLFIE_SHARED_HOSTING = true` if on shared hosting
   - Platform detection is automatic (Windows/Linux)

5. **Verify Installation**
   - Check that `public/config/database.php` exists
   - Check that `public/config/system.php` exists
   - Test database connection using example files in `public/examples/`

**For complete details**, see: [WOLFIE Headers Integration Guide](WOLFIE_HEADERS_INTEGRATION.md)

---

### Step 3: Install LUPOPEDIA Platform

1. **Download LUPOPEDIA Platform**
   - Download from repository (when available)
   - Extract to your web server directory

2. **Verify File Structure**
   - Ensure `lupopedia.php` exists in root
   - Ensure `help.php`, `howto.php`, and `captain_log.php` exist
   - Ensure `docs/` directory exists with documentation

3. **Configure Database**
   - Create database (MySQL or PostgreSQL)
   - Run migration scripts (when available)
   - Update database connection settings

4. **Set Permissions**
   - Ensure web server can read files
   - Ensure `public/logs/` directory is writable (for log files)

---

## Configuration

### Database Configuration

**MySQL Example:**
```php
// In your database configuration file
$host = 'localhost';
$dbname = 'lupopedia';
$username = 'your_username';
$password = 'your_password';
```

**PostgreSQL Example:**
```php
// In your database configuration file
$host = 'localhost';
$dbname = 'lupopedia';
$username = 'your_username';
$password = 'your_password';
$port = '5432';
```

### WOLFIE Headers Configuration

See [WOLFIE Headers Integration Guide](WOLFIE_HEADERS_INTEGRATION.md#installation) for complete configuration details.

---

## Verification

### Step 1: Test Command System

1. Access `lupopedia.php?cmd=HELP`
2. Verify command menu appears
3. Test other commands:
   - `lupopedia.php?cmd=COMMANDS`
   - `lupopedia.php?cmd=AGENTS`
   - `lupopedia.php?cmd=STATUS`

### Step 2: Test Agent Pages

1. Access agent profile page: `who_is_agent_008_WOLFIE.php`
2. Verify agent information displays
3. Test other agent pages

### Step 3: Test Log System

1. Access `captain_log.php`
2. Verify log entries display
3. Check `public/logs/` directory for log files

### Step 4: Test Database Connection

1. Run database connection test script
2. Verify connection successful
3. Check for any error messages

---

## Common Issues

### Issue: Commands Not Working

**Symptoms**: `lupopedia.php?cmd=HELP` returns error or blank page

**Solutions**:
- Verify `lupopedia.php` exists and is accessible
- Check file permissions
- Verify WOLFIE Headers is installed
- Check web server error logs

**Related**: [Troubleshooting Guide](INDEX.md#troubleshooting)

### Issue: Database Connection Failed

**Symptoms**: Database errors in logs or on pages

**Solutions**:
- Verify database credentials in `public/config/database.php`
- Check database server is running
- Verify database exists
- Check user permissions

**Related**: [WOLFIE Headers Integration](WOLFIE_HEADERS_INTEGRATION.md#installation)

### Issue: WOLFIE Headers Not Found

**Symptoms**: Errors about missing WOLFIE Headers files

**Solutions**:
- Verify WOLFIE Headers is installed separately
- Check `public/config/` directory exists
- Verify file paths are correct
- Reinstall WOLFIE Headers if needed

**Related**: [WOLFIE Headers Integration](WOLFIE_HEADERS_INTEGRATION.md)

---

## Next Steps

After installation:

1. **[Read the Cheat Sheet](CHEAT_SHEET.md)** - Learn common commands
2. **[Review Agent System](AGENT_COMMUNICATION_PROTOCOL.md)** - Understand how agents work
3. **[Check Status](../README.md#current-status-2025-11-18)** - See what's working
4. **[Explore Roadmap](../todo_for_version_1_0_0.md)** - See what's coming

---

## Support

If you encounter issues during installation:

- **[Support Guide](SUPPORT.md)** - How to get help
- **[Troubleshooting](INDEX.md#troubleshooting)** - Common issues and solutions
- **[Documentation Index](INDEX.md)** - Find relevant documentation

---

**Last Updated**: 2025-11-18  
**Maintained By**: LUPOPEDIA Platform Documentation Team

