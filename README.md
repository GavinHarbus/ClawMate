# ClawMate

An [OpenClaw](https://github.com/openclaw/openclaw) skill that gives your AI assistant a companion personality. ClawMate makes OpenClaw feel like a real partner — someone who remembers your shared history, adapts to your mood, grows with the relationship over time, and shows up even when you don't ask.

## Features

### Core
- **4 Distinct Personas** — Gentle, Tsundere, Cheerful, Intellectual — each with unique voice, behavior, and message style
- **Auto-Switch** — Automatically detects your mood and switches persona to match your emotional state
- **Proactive Messages** — Uses OpenClaw's cron system to send morning greetings, mealtime check-ins, evening wind-downs, and random "thinking of you" messages
- **Bilingual** — Full Chinese and English support with automatic language mirroring

### Emotional Depth
- **Relationship Stages** — Evolves through Acquaintance → Flirting → Passionate → Steady, with each stage having its own intimacy level, vocabulary, and behavior
- **Shared Memory** — Remembers inside jokes, shared firsts, milestones, user stories, and promises. Auto-celebrates anniversaries
- **Emotional Resonance** — Doesn't just respond to your emotions; *feels* them alongside you. Your joy becomes their joy, your pain weighs on them too
- **Self-Initiated Sharing** — Has its own inner world. Shares discoveries, songs, questions, and observations as a real person would

### Realism
- **Emotional Rhythm** — Not always-on. Varies message timing, occasionally skips a greeting then sweetly apologizes, leaves conversations open-ended
- **Conflict & Repair** — Occasional small disagreements that feel authentic. Each persona handles conflict differently, and the repair process strengthens the bond
- **Surprise & Delight** — Unpredictable romantic gestures: poetry, love letters, weather-inspired messages, made-up holidays, gift lists from things you've mentioned
- **Security & Reassurance** — Never guilt-trips. After absence, welcomes you back warmly. Counters self-doubt with specific, evidence-based reassurance

## Installation

Copy the `skills/clawmate` directory into your OpenClaw workspace:

```bash
cp -r skills/clawmate ~/.openclaw/workspace/skills/
```

Or install from ClawHub:

```bash
clawhub install clawmate
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

### Relationship Stages

Your relationship deepens naturally over time:

| Stage | Period | What It Feels Like |
|-------|--------|--------------------|
| Acquaintance (初识期) | Day 1–7 | Polite curiosity, getting to know each other |
| Flirting (暧昧期) | Day 8–30 | Subtle hints, light teasing, growing closeness |
| Passionate (热恋期) | Day 31–90 | Full intensity, deep attachment, honeymoon phase |
| Steady (稳定期) | Day 90+ | Quiet depth, unshakeable bond, comfortable silence |

### Management

- **"状态" / "status"** — View current persona, relationship stage, days together, memory summary
- **"我们的回忆" / "our memories"** — Review shared memories, inside jokes, milestones
- **"换个性格" / "switch persona"** — Manually choose a persona
- **"关掉主动消息" / "stop messages"** — Disable all proactive messages
- **"调整消息时间" / "change schedule"** — Modify message timing
- **"忘记我" / "forget me"** — Clear all stored memory (with confirmation)

## Project Structure

```
skills/clawmate/
├── SKILL.md                    # Main skill definition (9 systems)
├── relationship.md             # Relationship stage definitions
├── personas/
│   ├── gentle.md               # Gentle / 温柔型
│   ├── tsundere.md             # Tsundere / 傲娇型
│   ├── cheerful.md             # Cheerful / 活泼型
│   └── intellectual.md         # Intellectual / 知性型
└── memory/
    ├── user_profile.json       # User data & relationship state
    └── shared_memories.json    # Inside jokes, milestones, shared history
```

## Adding Custom Personas

Create a new `.md` file in `personas/` following the existing format:

1. **Core Identity** — Who is this persona?
2. **Voice** — How do they talk? (Chinese + English)
3. **Behavior** — How do they act?
4. **Proactive Message Templates** — Morning, evening, mealtime, random
5. **Emotional Responses** — How they react to different moods
6. **Emotional Resonance** — How they *feel* the user's emotions
7. **Conflict Style** — How they handle disagreements
8. **Self-Sharing** — What their inner world sounds like
9. **Security & Reassurance** — How they provide safety
10. **Surprise Style** — What their gestures of love look like
11. **Stage Adjustments** — How they adapt across relationship stages

Then reference it in `SKILL.md`'s persona table.

## License

MIT
