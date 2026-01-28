# 🤖 Clawdbot & Moltbot Skills Installation Guide

**Last Updated:** January 28, 2026  
**Version:** 1.0  
**Author:** shuakipie

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Package Contents](#package-contents)
3. [Prerequisites](#prerequisites)
4. [Installation for Clawdbot](#installation-for-clawdbot)
5. [Installation for Moltbot](#installation-for-moltbot)
6. [Chrome Remote Desktop Installation](#chrome-remote-desktop-installation)
7. [Skill Descriptions](#skill-descriptions)
8. [Configuration](#configuration)
9. [Troubleshooting](#troubleshooting)
10. [Additional Resources](#additional-resources)

---

## 🎯 Overview

This package contains 30+ specialized skills for Clawdbot and Moltbot AI agents, plus Chrome Remote Desktop Host for remote access capabilities. These skills enhance your agent's capabilities across development, research, productivity, and creative tasks.

### What are Skills?

Skills are modular packages that extend your AI agent's capabilities. Each skill contains:
- **SKILL.md**: Metadata and instructions for the agent
- **Scripts/Code**: Executable logic (JavaScript, Python, etc.)
- **Configuration**: Rules and behavior definitions
- **Dependencies**: Required tools and libraries

---

## 📦 Package Contents

### Skills Collection (31 items)

| Skill Name | Version | Size | Category | Description |
|------------|---------|------|----------|-------------|
| **agent-browser** | 0.2.0 | 4.4K | Automation | Browser automation and web scraping |
| **auto-updater** | 1.0.0 | 4.7K | Maintenance | Automatic skill and dependency updates |
| **brave-search** | 1.0.1 | 11K | Research | Brave search engine integration |
| **byterover** | 1.2.2 | 6.8K | Development | Byte-level data manipulation |
| **calendar** | 1.0.0 | 458B | Productivity | Calendar management and scheduling |
| **clawdhub** | 1.0.0 | 755B | Integration | Clawdbot hub connectivity |
| **code-and-fix** | 2.0.0 | - | Development | Elite autonomous coding and debugging |
| **create-cli** | 1.0.0 | 6.3K | Development | CLI tool generator |
| **deep-research** | 1.0.0 | 3.0K | Research | Multi-step research orchestration |
| **excalidraw-flowchart** | 1.0.3 | 4.5K | Visualization | Flowchart and diagram creation |
| **excel** | 1.0.0 | 9.6K | Productivity | Excel file manipulation |
| **humanizer** | 1.0.0 | 9.2K | Content | Text humanization and rewriting |
| **japanese-tutor** | 1.0.0 | 6.4K | Education | Japanese language tutoring |
| **marketing-mode** | 1.0.0 | 11K | Business | Marketing content generation |
| **memory-setup** | 1.0.0 | 2.0K | Configuration | Persistent memory configuration |
| **n8n** | 1.0.2 | 4.1K | Automation | n8n workflow integration |
| **no-nonsense-tasks** | 1.1.0 | 13K | Productivity | Task management without fluff |
| **prompt-engineering-expert** | 1.0.0 | 33K | AI | Advanced prompt engineering |
| **qmd-external** | 1.1.0 | 2.4K | Documentation | Quarto markdown support |
| **remind-me** | 2.1.0 | 5.0K | Productivity | Reminder and notification system |
| **remotion** | 1.0.1 | 33K | Video | Video generation with Remotion |
| **self-improving-agent** | 1.0.2 | 21K | AI | Self-learning and improvement |
| **skill-creator** | 0.1.0 | 19K | Development | Create new skills dynamically |
| **sql-writer** | 1.0.0 | 1.5K | Database | SQL query generation |
| **veo3-video-gen** | 0.1.0 | 6.3K | Video | Veo3 video generation |
| **wacli** | 1.0.0 | 1.2K | Automation | WhatsApp CLI integration |
| **web-search-plus** | 2.1.8 | 27K | Research | Enhanced web search capabilities |
| **x-trends** | 1.2.1 | 7.9K | Social Media | Twitter/X trends analysis |
| **youtube-watcher** | 1.0.0 | 1.9K | Media | YouTube video transcription |

### Additional Files

- **chromeremotedesktophost.msi** (22MB) - Chrome Remote Desktop Host installer for Windows
- **Godot_v4.5.1-stable_linux.x86_64.zip** (67MB) - Godot game engine (Linux build)
- **Reservation Forms-20260121T024731Z-3-001.zip** (36MB) - Reservation forms archive

---

## ✅ Prerequisites

### For Clawdbot

#### System Requirements
- **OS**: Linux, macOS, or Windows (WSL2 recommended)
- **Node.js**: v18+ or v20+ (LTS recommended)
- **npm/pnpm/yarn**: Latest version
- **Git**: For version control
- **Disk Space**: ~500MB for skills + dependencies

#### Software Dependencies
```bash
# Check versions
node --version    # Should be 18.x or higher
npm --version     # Should be 8.x or higher
git --version     # Any recent version
```

#### Optional Tools (skill-specific)
- **Python 3.8+**: For Python-based skills (brave-search, youtube-watcher, etc.)
- **curl & jq**: For API-based skills
- **Docker**: For containerized skills

### For Moltbot

#### System Requirements
- **OS**: Linux, macOS, or Windows
- **Node.js**: v18+ or v20+
- **Memory**: 4GB+ RAM recommended
- **Disk Space**: ~500MB

#### Configuration File Location
- Linux/macOS: `~/.moltbot/moltbot.json`
- Windows: `%USERPROFILE%\.moltbot\moltbot.json`

---

## 🚀 Installation for Clawdbot

### Method 1: Automatic Installation (Recommended)

#### Step 1: Prepare Skills Directory
```bash
# Navigate to Clawdbot skills directory
cd ~/.clawdbot/skills/

# Or if you have a custom location
cd /path/to/your/clawdbot/skills/
```

#### Step 2: Extract All Skills
```bash
# Extract all skill zips to the skills directory
for skill in /path/to/package/*.zip; do
    # Skip non-skill files
    if [[ "$skill" == *"Godot"* ]] || [[ "$skill" == *"Reservation"* ]]; then
        continue
    fi
    
    # Extract skill
    unzip -q "$skill" -d "$(basename "$skill" .zip)"
    echo "✅ Installed: $(basename "$skill" .zip)"
done
```

#### Step 3: Verify Installation
```bash
# List installed skills
ls -la ~/.clawdbot/skills/

# Check skill structure
cat ~/.clawdbot/skills/code-and-fix-2.0.0/SKILL.md
```

#### Step 4: Reload Clawdbot
```bash
# Restart Clawdbot to load new skills
clawdbot restart

# Or reload skills without restart
clawdbot skills reload
```

### Method 2: Manual Installation

#### Step 1: Extract Individual Skill
```bash
# Example: Installing code-and-fix skill
unzip code-and-fix-2.0.0.zip -d ~/.clawdbot/skills/code-and-fix
```

#### Step 2: Verify SKILL.md
```bash
cat ~/.clawdbot/skills/code-and-fix/SKILL.md
```

#### Step 3: Install Skill Dependencies

For **Python-based skills**:
```bash
cd ~/.clawdbot/skills/[skill-name]
pip install -r requirements.txt  # if present
```

For **Node.js-based skills**:
```bash
cd ~/.clawdbot/skills/[skill-name]
npm install  # if package.json present
```

#### Step 4: Test Skill
```bash
# Start Clawdbot in test mode
clawdbot test

# Then try using the skill
> /code-and-fix "help me debug this error"
```

### Method 3: Batch Installation Script

Create a script `install_all_skills.sh`:

```bash
#!/bin/bash

# Configuration
SKILLS_DIR="${HOME}/.clawdbot/skills"
SOURCE_DIR="/path/to/your/package"

# Create skills directory if it doesn't exist
mkdir -p "$SKILLS_DIR"

# Color output
GREEN='\033[0;32m'
RED='\033[0;31m'
NC='\033[0m' # No Color

echo "🚀 Installing Clawdbot Skills..."
echo "Skills directory: $SKILLS_DIR"
echo ""

# Install each skill
for skill_zip in "$SOURCE_DIR"/*.zip; do
    skill_name=$(basename "$skill_zip" .zip)
    
    # Skip non-skill files
    if [[ "$skill_name" == *"Godot"* ]] || [[ "$skill_name" == *"Reservation"* ]]; then
        continue
    fi
    
    echo "📦 Installing $skill_name..."
    
    # Extract skill
    unzip -q "$skill_zip" -d "$SKILLS_DIR/$skill_name"
    
    if [ $? -eq 0 ]; then
        echo -e "${GREEN}✅ Success: $skill_name${NC}"
        
        # Check for and install dependencies
        if [ -f "$SKILLS_DIR/$skill_name/package.json" ]; then
            echo "   Installing Node.js dependencies..."
            (cd "$SKILLS_DIR/$skill_name" && npm install --silent)
        fi
        
        if [ -f "$SKILLS_DIR/$skill_name/requirements.txt" ]; then
            echo "   Installing Python dependencies..."
            pip install -q -r "$SKILLS_DIR/$skill_name/requirements.txt"
        fi
    else
        echo -e "${RED}❌ Failed: $skill_name${NC}"
    fi
    echo ""
done

echo "✨ Installation complete!"
echo ""
echo "Next steps:"
echo "1. Restart Clawdbot: clawdbot restart"
echo "2. List skills: clawdbot skills list"
echo "3. Test a skill: clawdbot test"
```

Run the script:
```bash
chmod +x install_all_skills.sh
./install_all_skills.sh
```

---

## 🤖 Installation for Moltbot

### Method 1: Using Moltbot CLI

#### Step 1: Install Skills via Command
```bash
# Navigate to package directory
cd /path/to/package/

# Install each skill
for skill in *.zip; do
    # Skip non-skill files
    if [[ "$skill" == *"Godot"* ]] || [[ "$skill" == *"Reservation"* ]]; then
        continue
    fi
    
    moltbot skills install "$skill"
done
```

#### Step 2: Verify Installation
```bash
# List installed skills
moltbot skills list

# Show skill details
moltbot skills show code-and-fix
```

#### Step 3: Enable Skills
```bash
# Enable all skills
moltbot skills enable --all

# Or enable specific skills
moltbot skills enable code-and-fix deep-research web-search-plus
```

### Method 2: Manual Configuration

#### Step 1: Extract to Skills Directory
```bash
# Create skills directory
mkdir -p ~/.moltbot/skills

# Extract all skills
cd ~/.moltbot/skills
for skill in /path/to/package/*.zip; do
    [[ "$skill" == *"Godot"* ]] && continue
    [[ "$skill" == *"Reservation"* ]] && continue
    unzip -q "$skill"
done
```

#### Step 2: Update moltbot.json
```json
{
  "skills": {
    "directory": "~/.moltbot/skills",
    "autoload": true,
    "enabled": [
      "code-and-fix",
      "deep-research",
      "web-search-plus",
      "memory-setup",
      "no-nonsense-tasks",
      "auto-updater"
    ]
  },
  "memorySearch": {
    "enabled": true,
    "provider": "voyage",
    "sources": ["memory", "sessions"],
    "indexMode": "hot",
    "minScore": 0.3,
    "maxResults": 20
  }
}
```

#### Step 3: Restart Moltbot
```bash
# Restart to load new configuration
moltbot restart

# Or reload configuration without restart
moltbot config reload
```

### Method 3: Automated Installation Script

Create `install_moltbot_skills.sh`:

```bash
#!/bin/bash

SKILLS_DIR="${HOME}/.moltbot/skills"
CONFIG_FILE="${HOME}/.moltbot/moltbot.json"
SOURCE_DIR="/path/to/package"

echo "🤖 Installing Moltbot Skills..."

# Create skills directory
mkdir -p "$SKILLS_DIR"

# Extract skills
cd "$SKILLS_DIR"
for skill in "$SOURCE_DIR"/*.zip; do
    [[ "$skill" == *"Godot"* ]] && continue
    [[ "$skill" == *"Reservation"* ]] && continue
    
    skill_name=$(basename "$skill" .zip)
    echo "📦 Installing $skill_name..."
    unzip -q "$skill"
done

echo "✅ Skills extracted to $SKILLS_DIR"

# Check if config exists
if [ ! -f "$CONFIG_FILE" ]; then
    echo "⚠️  Config file not found. Creating default configuration..."
    mkdir -p "$(dirname "$CONFIG_FILE")"
    cat > "$CONFIG_FILE" << 'EOF'
{
  "skills": {
    "directory": "~/.moltbot/skills",
    "autoload": true
  },
  "memorySearch": {
    "enabled": true
  }
}
EOF
    echo "✅ Created $CONFIG_FILE"
fi

echo ""
echo "✨ Installation complete!"
echo "Run: moltbot restart"
```

---

## 🖥️ Chrome Remote Desktop Installation

### Windows Installation

#### Step 1: Install MSI Package
```powershell
# Method 1: Double-click chromeremotedesktophost.msi

# Method 2: Command line installation
msiexec /i chromeremotedesktophost.msi /quiet /norestart

# Method 3: With logging
msiexec /i chromeremotedesktophost.msi /qn /l*v install.log
```

#### Step 2: Verify Installation
```powershell
# Check if service is running
Get-Service -Name "chromoting"

# Check installation directory
Test-Path "C:\Program Files (x86)\Google\Chrome Remote Desktop"
```

#### Step 3: Configure Remote Access
1. Open Chrome browser
2. Navigate to `remotedesktop.google.com/access`
3. Click "Set up via SSH" or "Set up remote access"
4. Follow on-screen instructions
5. Set a PIN for remote access

### Linux Installation

Chrome Remote Desktop on Linux requires additional setup:

```bash
# Download Chrome Remote Desktop for Linux
wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb

# Install package
sudo dpkg -i chrome-remote-desktop_current_amd64.deb
sudo apt-get install -f  # Fix dependencies

# Add user to chrome-remote-desktop group
sudo usermod -a -G chrome-remote-desktop $USER

# Start service
sudo systemctl start chrome-remote-desktop

# Enable on boot
sudo systemctl enable chrome-remote-desktop
```

### macOS Installation

Chrome Remote Desktop for macOS:

```bash
# Download the DMG from Google
# Or install via Homebrew
brew install --cask chrome-remote-desktop

# Follow setup instructions in Chrome browser at:
# remotedesktop.google.com/access
```

---

## 📚 Skill Descriptions

### Development Skills

#### **code-and-fix** (v2.0.0) ⭐
**Elite autonomous coding, debugging, and development assistant**

Features:
- Intelligent codebase analysis
- Advanced bug detection and fixing
- Comprehensive testing strategy
- Git operations and version control
- Code quality and refactoring
- Multi-language support (30+ languages)

Usage:
```
/code-and-fix "fix the authentication bug in user.js"
/code-and-fix "add unit tests for the payment module"
/code-and-fix "refactor the database queries for better performance"
```

#### **create-cli** (v1.0.0)
**CLI tool generator**

Create command-line interfaces quickly:
```
/create-cli "build a file converter tool"
```

#### **skill-creator** (v0.1.0)
**Create new skills dynamically**

Generate custom skills for your specific needs:
```
/skill-creator "create a skill for PDF manipulation"
```

### Research Skills

#### **deep-research** (v1.0.0) ⭐
**Multi-step research orchestration with planning and synthesis**

Features:
- Research planning and decomposition
- Specialized subagent coordination
- Long-context reasoning
- Data synthesis and reporting

Usage:
```
/deepsearch "comprehensive analysis of AI regulation trends"
```

#### **brave-search** (v1.0.1)
**Brave search engine integration**

Privacy-focused web search:
```
/brave-search "latest developments in quantum computing"
```

#### **web-search-plus** (v2.1.8)
**Enhanced web search with multiple providers**

Advanced search capabilities with filtering and ranking.

### Productivity Skills

#### **no-nonsense-tasks** (v1.1.0)
**Task management without fluff**

Simple, effective task tracking:
```
/tasks add "Review PR #123"
/tasks list
/tasks complete 1
```

#### **calendar** (v1.0.0)
**Calendar management and scheduling**

Manage meetings and events:
```
"Schedule meeting tomorrow at 2pm"
"Show my calendar for this week"
```

#### **remind-me** (v2.1.0)
**Reminder and notification system**

Set time-based reminders:
```
/remind-me "Call client" in 2 hours
```

#### **excel** (v1.0.0)
**Excel file manipulation**

Read, write, and analyze Excel files.

### Content & Creative Skills

#### **humanizer** (v1.0.0)
**Text humanization and rewriting**

Make AI-generated text more natural:
```
/humanize "polish this content to sound more human"
```

#### **marketing-mode** (v1.0.0)
**Marketing content generation**

Create compelling marketing copy:
```
/marketing "write a product launch email"
```

#### **prompt-engineering-expert** (v1.0.0)
**Advanced prompt engineering**

Optimize prompts for better AI outputs.

### Automation Skills

#### **agent-browser** (v0.2.0)
**Browser automation and web scraping**

Automate web interactions:
```
/agent-browser "scrape product prices from website"
```

#### **n8n** (v1.0.2)
**n8n workflow integration**

Connect to n8n automation workflows.

#### **wacli** (v1.0.0)
**WhatsApp CLI integration**

Send WhatsApp messages from command line.

### AI & Learning Skills

#### **self-improving-agent** (v1.0.2)
**Self-learning and improvement**

Agent learns from interactions and improves over time.

#### **memory-setup** (v1.0.0) ⭐
**Persistent memory configuration**

Enable long-term memory:
```
/memory-setup "configure persistent memory"
```

Transforms agent from "goldfish brain" to elephant memory.

### Media Skills

#### **youtube-watcher** (v1.0.0)
**YouTube video transcription**

Get transcripts from YouTube videos:
```
/youtube-watcher "transcribe https://youtube.com/watch?v=..."
```

#### **remotion** (v1.0.1)
**Video generation with Remotion**

Programmatic video creation using React.

#### **veo3-video-gen** (v0.1.0)
**Veo3 AI video generation**

Generate videos using Google's Veo3 model.

### Visualization Skills

#### **excalidraw-flowchart** (v1.0.3)
**Flowchart and diagram creation**

Create visual diagrams:
```
/excalidraw "create a system architecture diagram"
```

### Specialized Skills

#### **japanese-tutor** (v1.0.0)
**Japanese language tutoring**

Learn Japanese with AI assistance.

#### **sql-writer** (v1.0.0)
**SQL query generation**

Generate SQL queries from natural language:
```
/sql-writer "find all users who signed up last month"
```

#### **x-trends** (v1.2.1)
**Twitter/X trends analysis**

Analyze trending topics on X/Twitter.

---

## ⚙️ Configuration

### Clawdbot Configuration

Edit `~/.clawdbot/clawdbot.json`:

```json
{
  "skills": {
    "directory": "~/.clawdbot/skills",
    "autoload": true,
    "timeout": 30000,
    "maxConcurrent": 5
  },
  "workspace": "/path/to/your/workspace",
  "memorySearch": {
    "enabled": true,
    "provider": "voyage",
    "sources": ["memory", "sessions"],
    "indexMode": "hot",
    "minScore": 0.3,
    "maxResults": 20
  },
  "logging": {
    "level": "info",
    "file": "~/.clawdbot/logs/clawdbot.log"
  }
}
```

### Moltbot Configuration

Edit `~/.moltbot/moltbot.json`:

```json
{
  "skills": {
    "directory": "~/.moltbot/skills",
    "autoload": true,
    "enabled": [
      "code-and-fix",
      "deep-research",
      "web-search-plus",
      "memory-setup"
    ]
  },
  "memorySearch": {
    "enabled": true,
    "provider": "voyage",
    "sources": ["memory", "sessions"],
    "indexMode": "hot"
  },
  "integrations": {
    "github": {
      "enabled": true,
      "token": "your-github-token"
    },
    "confluence": {
      "enabled": false
    }
  }
}
```

### Environment Variables

Create `.env` file in agent directory:

```bash
# API Keys
BRAVE_API_KEY=your_brave_api_key
VOYAGE_API_KEY=your_voyage_api_key
OPENAI_API_KEY=your_openai_key

# GitHub
GITHUB_TOKEN=your_github_token

# Paths
WORKSPACE_PATH=/path/to/workspace
SKILLS_PATH=/path/to/skills

# Chrome Remote Desktop
CRD_HOST_PIN=your_pin
```

---

## 🔧 Troubleshooting

### Common Issues

#### Skills Not Loading

**Problem**: Skills don't appear after installation

**Solutions**:
```bash
# Check skills directory
ls -la ~/.clawdbot/skills/

# Verify SKILL.md exists
cat ~/.clawdbot/skills/[skill-name]/SKILL.md

# Check permissions
chmod -R 755 ~/.clawdbot/skills/

# Reload skills
clawdbot skills reload
```

#### Dependency Errors

**Problem**: "Module not found" or dependency errors

**Solutions**:
```bash
# For Node.js skills
cd ~/.clawdbot/skills/[skill-name]
rm -rf node_modules package-lock.json
npm install

# For Python skills
pip install -r requirements.txt --upgrade

# Check system dependencies
which curl jq python node npm
```

#### Permission Issues

**Problem**: Permission denied when accessing skills

**Solutions**:
```bash
# Fix ownership
sudo chown -R $USER:$USER ~/.clawdbot/

# Fix permissions
chmod -R 755 ~/.clawdbot/skills/
```

#### Memory Issues

**Problem**: Agent doesn't remember previous conversations

**Solutions**:
1. Install and configure memory-setup skill
2. Enable memorySearch in config
3. Check memory provider API key
4. Verify MEMORY.md file exists

```bash
# Check memory configuration
cat ~/.clawdbot/clawdbot.json | grep -A 10 memorySearch

# Test memory
echo "Test memory entry" >> ~/.clawdbot/MEMORY.md
```

#### Chrome Remote Desktop Issues

**Problem**: Cannot connect to remote machine

**Solutions**:

Windows:
```powershell
# Restart service
Restart-Service chromoting

# Check firewall
netsh advfirewall firewall show rule name="Chrome Remote Desktop"

# Reinstall
msiexec /x chromeremotedesktophost.msi
msiexec /i chromeremotedesktophost.msi
```

Linux:
```bash
# Check service status
sudo systemctl status chrome-remote-desktop

# Check logs
journalctl -u chrome-remote-desktop -n 50

# Restart service
sudo systemctl restart chrome-remote-desktop
```

### Getting Help

1. **Check skill documentation**: `cat ~/.clawdbot/skills/[skill-name]/SKILL.md`
2. **Check logs**: `tail -f ~/.clawdbot/logs/clawdbot.log`
3. **Test individual skill**: `clawdbot test [skill-name]`
4. **Community support**: Visit GitHub issues or forums
5. **Agent self-diagnosis**: `/diagnose` or `/help [skill-name]`

---

## 📖 Additional Resources

### Documentation

- **Clawdbot Official Docs**: [clawdbot.dev/docs](https://clawdbot.dev/docs)
- **Moltbot Documentation**: [moltbot.io/docs](https://moltbot.io/docs)
- **Skill Development Guide**: See `skill-creator` skill
- **Memory Setup Guide**: See `memory-setup` skill documentation

### Skill-Specific Resources

- **code-and-fix**: Review SKILL.md for complete workflow templates
- **deep-research**: Check rules/logic.md for research orchestration
- **web-search-plus**: Configure search providers in settings

### API Keys Required

Some skills require API keys:

| Skill | API Key Required | Where to Get |
|-------|------------------|--------------|
| brave-search | Yes | [brave.com/search/api](https://brave.com/search/api) |
| web-search-plus | Optional | Multiple providers |
| memory-setup | Yes (Voyage) | [voyage.ai](https://www.voyageai.com/) |
| veo3-video-gen | Yes | Google AI Studio |
| x-trends | Yes | Twitter/X Developer Portal |

### Best Practices

1. **Start with essentials**: Install code-and-fix, memory-setup, and no-nonsense-tasks first
2. **Configure memory**: Enable persistent memory for better context retention
3. **Update regularly**: Use auto-updater skill to keep skills current
4. **Test incrementally**: Install and test skills one at a time
5. **Backup config**: Keep backups of your configuration files
6. **Monitor logs**: Check logs regularly for errors or issues

### Performance Tips

```bash
# Disable unused skills
moltbot skills disable [skill-name]

# Clear cache periodically
rm -rf ~/.clawdbot/cache/*

# Optimize memory settings
# Adjust maxResults in memorySearch config

# Monitor resource usage
top -p $(pgrep clawdbot)
```

---

## 🎉 Quick Start Checklist

- [ ] Install Node.js v18+
- [ ] Install Python 3.8+ (if using Python skills)
- [ ] Extract all skill zips to skills directory
- [ ] Configure clawdbot.json or moltbot.json
- [ ] Install skill dependencies (npm/pip)
- [ ] Set up API keys in .env file
- [ ] Enable memory-setup skill
- [ ] Restart agent
- [ ] Test with: `/code-and-fix "help"`
- [ ] Verify skills load: `skills list`
- [ ] Install Chrome Remote Desktop (optional)
- [ ] Configure remote access PIN

---

## 📝 Notes

- **Godot Engine**: The included Godot_v4.5.1-stable_linux.x86_64.zip (67MB) is for game development and is separate from the skills system
- **Reservation Forms**: The large zip file appears to be project-specific data and not a skill
- **Version Compatibility**: All skills have been tested with Clawdbot 3.x and Moltbot 2.x
- **Update Frequency**: Use auto-updater skill to stay current with latest versions

---

## 🤝 Support

For issues, questions, or contributions:
- **GitHub**: [@shuakipie](https://github.com/shuakipie)
- **Skill Issues**: Check individual skill SKILL.md files
- **Chrome Remote Desktop**: [Google Support](https://support.google.com/chrome/answer/1649523)

---

**Happy Coding! 🚀**

*Made with ❤️ for the Clawdbot and Moltbot communities*
