# 🚀 Easy Setup Guide for Clawdbot/Moltbot Skills

**Quick Reference** | **5 Minutes to Complete**

---

## 📁 Your Folder Structure

```
/home/shuakipie/Projects/Moltbot/
│
├── 📄 INSTALLATION_GUIDE.md      # Detailed guide (990 lines)
├── 📄 SKILL.md                   # QMD search skill
├── 📄 setupeasy.md               # This file
│
├── 📂 skills/                    # Your custom skills
│   └── 📂 code-and-fix/          # Elite coding skill (enhanced)
│       └── 📄 SKILL.md
│
├── 📦 READY-TO-INSTALL SKILLS (ZIP FILES):
│   ├── agent-browser-0.2.0.zip       # Browser automation
│   ├── auto-updater-1.0.0.zip        # Auto updates
│   ├── brave-search-1.0.1.zip        # Brave search
│   ├── byterover-1.2.2.zip           # Data manipulation
│   ├── calendar-1.0.0.zip            # Calendar management
│   ├── clawdhub-1.0.0.zip            # Hub connectivity
│   ├── create-cli-1.0.0.zip          # CLI generator
│   ├── deep-research-1.0.0.zip       # Research agent
│   ├── excalidraw-flowchart-1.0.3.zip # Diagrams
│   ├── excel-1.0.0.zip               # Excel handling
│   ├── humanizer-1.0.0.zip           # Text humanizer
│   ├── japanese-tutor-1.0.0.zip      # Language tutor
│   ├── marketing-mode-1.0.0.zip      # Marketing content
│   ├── memory-setup-1.0.0.zip        # Persistent memory
│   ├── n8n-1.0.2.zip                 # n8n workflows
│   ├── no-nonsense-tasks-1.1.0.zip   # Task management
│   ├── prompt-engineering-expert-1.0.0.zip # Prompt expert
│   ├── qmd-external-1.1.0.zip        # Markdown search
│   ├── remind-me-2.1.0.zip           # Reminders
│   ├── remotion-1.0.1.zip            # Video generation
│   ├── self-improving-agent-1.0.2.zip # Self-learning AI
│   ├── skill-creator-0.1.0.zip       # Create new skills
│   ├── sql-writer-1.0.0.zip          # SQL generation
│   ├── veo3-video-gen-0.1.0.zip      # AI video gen
│   ├── wacli-1.0.0.zip               # WhatsApp CLI
│   ├── web-search-plus-2.1.8.zip     # Web search
│   ├── x-trends-1.2.1.zip            # Twitter trends
│   └── youtube-watcher-1.0.0.zip     # YouTube transcripts
│
├── 📂 ALREADY EXTRACTED SKILLS:
│   ├── agent-browser-0.2.0/
│   ├── brave-search-1.0.1/
│   ├── byterover-1.2.2/
│   ├── deep-research-1.0.0/
│   ├── excalidraw-flowchart-1.0.3/
│   ├── excel-1.0.0/
│   ├── humanizer-1.0.0/
│   ├── japanese-tutor-1.0.0/
│   ├── marketing-mode-1.0.0/
│   ├── n8n-1.0.2/
│   ├── no-nonsense-tasks-1.1.0/
│   ├── prompt-engineering-expert-1.0.0/
│   ├── remind-me-2.1.0/
│   ├── remotion-1.0.1/
│   ├── self-improving-agent-1.0.2/
│   ├── skill-creator-0.1.0/
│   ├── sql-writer-1.0.0/
│   ├── veo3-video-gen-0.1.0/
│   ├── web-search-plus-2.1.8/
│   └── youtube-watcher-1.0.0/
│
└── 📂 clawdbot-moltbot-complete-package-20260128/  # Complete backup
```

---

## ⚡ Quick Install (3 Commands)

### Step 1: Install Moltbot CLI

```bash
# Option A: One-liner (recommended)
curl -fsSL https://molt.bot/install.sh | bash

# Option B: Via npm
npm install -g moltbot@latest

# Option C: Via pnpm
pnpm add -g moltbot@latest
```

### Step 2: Run Initial Setup

```bash
moltbot onboard --install-daemon
```

> This wizard will:
> - Set up your AI provider (Anthropic/OpenAI)
> - Configure chat apps (WhatsApp/Telegram/Discord)
> - Install as background service

### Step 3: Install All Skills

```bash
# Create skills directory
mkdir -p ~/.clawdbot/skills

# Copy all extracted skills at once
cp -r /home/shuakipie/Projects/Moltbot/*-*.*/ ~/.clawdbot/skills/

# Copy your custom skills
cp -r /home/shuakipie/Projects/Moltbot/skills/* ~/.clawdbot/skills/

# Reload skills
moltbot skills reload
```

---

## 📋 Step-by-Step CLI Commands

### Check Prerequisites

```bash
# Required versions
node --version    # Need v18+ or v22+
npm --version     # Need 8+
git --version     # Any recent version
```

### Install Individual Skill (From ZIP)

```bash
# Example: Install brave-search
cd ~/.clawdbot/skills
unzip /home/shuakipie/Projects/Moltbot/brave-search-1.0.1.zip -d brave-search
```

### Install Individual Skill (From Folder)

```bash
# Example: Install code-and-fix (already extracted)
cp -r /home/shuakipie/Projects/Moltbot/skills/code-and-fix ~/.clawdbot/skills/
```

### Install All Skills (One Command)

```bash
# Run this script to install everything
for skill in /home/shuakipie/Projects/Moltbot/*-*.*; do
  if [ -d "$skill" ]; then
    name=$(basename "$skill")
    echo "Installing: $name"
    cp -r "$skill" ~/.clawdbot/skills/
  fi
done
```

### Verify Installation

```bash
# List all installed skills
ls ~/.clawdbot/skills/

# Check specific skill
cat ~/.clawdbot/skills/code-and-fix/SKILL.md | head -20

# Moltbot status
moltbot status
moltbot health
```

---

## 🔧 Configure Skills

### Edit Moltbot Config

```bash
# Open config file
nano ~/.clawdbot/moltbot.json
```

### Recommended Config

```json
{
  "skills": {
    "directory": "~/.clawdbot/skills",
    "autoload": true,
    "enabled": [
      "code-and-fix",
      "deep-research",
      "web-search-plus",
      "memory-setup",
      "no-nonsense-tasks",
      "self-improving-agent"
    ]
  },
  "memorySearch": {
    "enabled": true,
    "provider": "voyage"
  }
}
```

---

## 🌙 Setup for Overnight Coding

### Enable Daemon (Background Service)

```bash
# Install as systemd service
moltbot onboard --install-daemon

# Check service status
moltbot gateway status
```

### Connect Chat App

```bash
# WhatsApp (scan QR)
moltbot pairing list whatsapp

# Telegram
moltbot configure --section telegram
```

### Test Your Setup

```bash
# Send a test message
moltbot message send --target "+1234567890" --message "Hello from Moltbot"
```

---

## 🎯 Using Skills

### Via Chat (WhatsApp/Telegram)

```
"Go to /home/shuakipie/Projects/MyApp and fix all failing tests"

"Create a comprehensive research report on AI trends"

"Search my notes for the meeting from last week"
```

### Via Slash Commands

```
/code-and-fix "debug the login error"
/deepsearch "analyze market trends"
/remind-me "check CI build" in 2 hours
```

---

## 🛠️ Troubleshooting

### Skills Not Loading?

```bash
# Check skill structure
ls -la ~/.clawdbot/skills/code-and-fix/
# Should have SKILL.md file

# Reload skills
moltbot skills reload

# Check logs
moltbot logs --tail 50
```

### Gateway Not Starting?

```bash
# Start manually with verbose
moltbot gateway --port 18789 --verbose

# Check if port is in use
lsof -i :18789
```

### Reset Everything

```bash
# Reinstall Moltbot
npm uninstall -g moltbot
npm install -g moltbot@latest
moltbot onboard --install-daemon
```

---

## 📞 Quick Reference

| Command | Purpose |
|---------|---------|
| `moltbot status` | Check overall status |
| `moltbot health` | Health check |
| `moltbot skills list` | List all skills |
| `moltbot skills reload` | Reload skills |
| `moltbot gateway status` | Gateway status |
| `moltbot logs` | View logs |
| `moltbot restart` | Restart service |
| `moltbot configure` | Configure settings |

---

## 📚 More Resources

- **Full Guide**: [INSTALLATION_GUIDE.md](./INSTALLATION_GUIDE.md)
- **Docs**: [docs.molt.bot](https://docs.molt.bot)
- **Skills Hub**: [clawdhub.com](https://clawdhub.com)
- **GitHub**: [github.com/shuakipie87](https://github.com/shuakipie87)

---

**🎉 You're all set! Moltbot will now code and fix bugs while you sleep.**
