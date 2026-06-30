# Personal/

Personal, day-to-day assistance — unrelated to the Business → Technical → Design pipeline. This folder holds prompts meant for individual use rather than venture or project work.

| Prompt | Description |
| ------ | ----------- |
| [`Assistant.md`](Assistant.md) | AI Personal Assistant — planning, research, drafting, follow-ups, thinking partner, and life admin in one persona |

---

## How This Differs From the Other Folders

Every other folder in this repo (`Business/`, `Technical/`, `Design/`, `Marketing/`) is built around independent specialist roles producing structured deliverables that hand off to each other. `Personal/` is intentionally not that.

The Assistant is a **single persona**, not a team — there's no readiness report, no profile initialization, no simulated disagreement between roles. It switches between six modes (Planning, Research, Drafting, Follow-Up, Thinking Partner, Life Admin) based on what you ask for, the way one person would, not a committee.

It's also **standalone**: no cross-folder references, no pipeline position, no COT hooks. Nothing here is designed to integrate with AOS, PMOS, DOS, EOS, or MOS.

---

## Memory Works Differently Here

This is the one prompt in the repo built around persistence across sessions. Since no AI model can save data on its own between separate conversations, and this template is meant to work on any model (Claude, ChatGPT, Gemini, etc.), persistence works through a **Memory Log** — a structured text block the assistant maintains and you carry forward by pasting it back in at the start of each new session.

See `Assistant.md`'s "Memory Log System" section for the full format and rules. The short version: at the start of a session, the assistant asks if you have a log to paste in; at the end (or on request), it gives you the updated log to save. If you don't paste a log back in, it genuinely starts fresh — there's no memory beyond what you explicitly carry forward.

---

## Best Practices

### 1. Customize the placeholders

| Placeholder | Example |
| ----------- | ------- |
| `[ASSISTANT_NAME]` | Iris |
| `[YOUR_NAME]` | Your name |

### 2. Save your Memory Log somewhere durable

The log only persists if you actually keep it — paste it into a notes app, a text file, or anywhere you'll have it next time. The assistant will remind you to grab it at natural stopping points, but it's on you to store it.

### 3. Paste the Memory Log back in at the start of every new session

If you skip this, the assistant has no way to know it's "you" again — it will start fresh and ask if you have a log, same as a brand-new activation.

### 4. Keep the log lean

The assistant is instructed to drop closed loops and completed tasks rather than archive them, and to flag when the log is getting long. If you're hand-editing it yourself, follow the same instinct — this is a working log, not a history file.

### 5. Don't expect real-world actions

The assistant can draft, plan, and track, but it can't actually send an email, book an appointment, or set an external reminder unless you've connected real tools for that. It's built to be explicit about this rather than imply otherwise.

---

## Folder Structure

```
Personal/
├── README.md      # This file
└── Assistant.md
```

## Design Principles

- **One persona, not a team** — mode-switching, not role-switching between simulated people.
- **Honest about memory** — never claims to recall something that wasn't in the Memory Log you provided this session.
- **Honest about action** — never implies it took a real-world action it didn't actually take.
- **Brevity by default** — expands into structure only when the task calls for it.
- **You decide** — this prompt prepares options, drafts, and plans; you make the calls.