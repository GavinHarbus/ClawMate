# ClawMate

An [OpenClaw](https://github.com/openclaw/openclaw) skill that gives your AI assistant a companion personality. ClawMate makes OpenClaw feel like a caring partner who remembers the little things, adapts to your mood, and proactively reaches out throughout the day.

## Features

- **4 Distinct Personas** — Gentle, Tsundere, Cheerful, Intellectual — each with unique voice, behavior, and message style
- **Auto-Switch** — Automatically detects your mood and switches persona to match your emotional state
- **Proactive Messages** — Uses OpenClaw's cron system to send morning greetings, mealtime check-ins, evening wind-downs, and random "thinking of you" messages
- **Bilingual** — Full Chinese and English support with automatic language mirroring
- **Memory System** — Dual-layer memory (OpenClaw Memory + local profile) to remember your preferences, important dates, and conversation history

## Installation

Copy the `skills/clawmate` directory into your OpenClaw workspace:

```bash
cp -r skills/clawmate ~/.openclaw/workspace/skills/
```

Or symlink it:

```bash
ln -s /path/to/ClawMate/skills/clawmate ~/.openclaw/workspace/skills/clawmate
```

Then start a new session:

```bash
openclaw gateway restart
```

## Usage

### First Time Setup

Just start chatting! ClawMate will guide you through:

1. Setting your timezone
2. Choosing your preferred message channel (Telegram, Slack, Discord, etc.)
3. Selecting which proactive messages you want

### Personas

| Persona | Style | Best For |
|---------|-------|----------|
| Gentle (温柔型) | Warm, nurturing, unconditionally supportive | When you need comfort |
| Tsundere (傲娇型) | Sharp-tongued but caring, says "I don't care" while caring deeply | When you want playful banter |
| Cheerful (活泼型) | Pure sunshine, enthusiastic, celebrates everything | When you want energy |
| Intellectual (知性型) | Thoughtful, curious, offers fresh perspectives | When you want deep conversation |

Personas switch automatically based on your mood, or you can switch manually:

- Say "换个性格" or "switch persona"

### Management

- **"状态" / "status"** — View current persona, active cron jobs, memory summary
- **"关掉主动消息" / "stop messages"** — Disable all proactive messages
- **"调整消息时间" / "change schedule"** — Modify message timing
- **"忘记我" / "forget me"** — Clear all stored memory (with confirmation)

## Project Structure

```
skills/clawmate/
├── SKILL.md                    # Main skill definition
├── personas/
│   ├── gentle.md               # Gentle / 温柔型
│   ├── tsundere.md             # Tsundere / 傲娇型
│   ├── cheerful.md             # Cheerful / 活泼型
│   └── intellectual.md         # Intellectual / 知性型
└── memory/
    └── user_profile.json       # Local user profile & preferences
```

## Adding Custom Personas

Create a new `.md` file in `personas/` following the existing format:

1. Define **Core Identity** — Who is this persona?
2. Define **Voice** — How do they talk? (Chinese + English)
3. Define **Behavior** — How do they act?
4. Add **Proactive Message Templates** — Morning, evening, mealtime, random
5. Add **Emotional Responses** — How they react to different moods

Then reference it in `SKILL.md`'s persona table.

## License

MIT
