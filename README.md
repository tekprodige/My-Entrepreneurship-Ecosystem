# My-Entrepreneurship-Ecosystem

An interconnected ecosystem of AI prompts for running a venture end to end — from initial opportunity evaluation through executive oversight, product definition, design, engineering, marketing, and day-to-day personal support. Each prompt is a structured system prompt built for use in LLM chat sessions (Cursor, ChatGPT, Claude, and similar tools), and several are designed to hand off deliverables to one another.

This repo grows over time. Prompts are organized by category so you can browse, copy, and adapt them for your own work.

## What's New in v3

v3 is an efficiency release — every operating system was restructured based on real-world use so sessions start faster, cost fewer tokens, and produce leaner outputs.

- **Fast start** — Teams now open with a single compact message: a roster table, a one-line ready confirmation, and a request for your first input. The long introductions and readiness reports from v2 are gone.
- **Adaptive deliverables** — Every deliverable (ERP, EPD, DSP, TDP, BTP, FTP, DOTP, SAP, GTM/MSD, EOP) now generates only the sections relevant to the task, closing with a one-line list of what was omitted. A small feature request gets a short package; a full system gets a full one.
- **Condensed boilerplate** — Profile Standards and continuity rules were cut from tables-plus-paragraphs down to a few sentences, without losing the two guarantees that matter: role consistency within a session, and no false claims of cross-session memory.
- **Single-conversation rule everywhere** — EOS's old one-thread-per-engineer instruction (a v2.1 leftover) was replaced. Every OS now runs its full team in one conversation, with structured deliverables as the only thing that crosses between threads.
- **What didn't change** — Board Operating Rules and the disagreement mechanic are fully intact. Specialists still think independently, still disagree openly, and managers still document conflicts rather than resolving them. Efficiency cuts ceremony, not judgment.

New since v2 launched: **BOS** (backend), **FOS** (frontend), **DOOS** (DevOps), and **CYOS** (cybersecurity) — four lean, dedicated engineering teams that can replace or complement the full EOS org. AOS also split into standalone **For-Profit** and **Non-Profit** editions.

## Prompt Directory

| Category | Description | Prompts |
| -------- | ----------- | ------- |
| [**Business/**](Business/) | Executive oversight and opportunity advisory | [AOS — For-Profit](Business/AOS-ForProfit.md) · [AOS — Non-Profit](Business/AOS-NonProfit.md) · [COT](Business/COT.md) |
| [**Technical/**](Technical/) | Product management, engineering, and security planning | [PMOS](Technical/PMOS.md) · [EOS](Technical/EOS.md) · [BOS](Technical/BOS.md) · [FOS](Technical/FOS.md) · [DOOS](Technical/DOOS.md) · [CYOS](Technical/CYOS.md) |
| [**Marketing/**](Marketing/) | Go-to-market and brand strategy | [MOS](Marketing/MOS.md) |
| [**Design/**](Design/) | Design specification and handoff | [DOS](Design/DOS.md) |
| [**Personal/**](Personal/) | Personal assistance and founder utilities (standalone) | [Assistant](Personal/Assistant.md) · [Company Briefing](Personal/Company-Briefing.md) |

*More categories and prompts will be added here as they are developed.*

Each category folder has its own README with prompt-specific best practices, structure, and design principles. Start there once you've picked a category.

**Fastest way to start:** use the [Universal Activation Prompt](Activation-Prompt.md). Fill in three fields — your name, your title, your company — and paste it into a new chat with any OS file. The AI generates a fitting fictitious name and personality for every role, so you skip filling the `[*_NAME]` placeholders by hand, and the team knows who the Project Owner is from message one. Two tips: names don't persist between conversations, so if you like a generated team, note the names and add "Use these names: …" next time; and if a personality ever starts overriding a specialist's judgment (an optimistic CFO who stops flagging risk), remind the team that role responsibilities outrank personality.

---

## How the Categories Relate

These prompts aren't fully independent — several are designed to hand off deliverables to each other, even across folders.

```
                    COT (Business/) — Founder's Executive Layer
              (CEO · COO · CFO · CTO · CMO · CPO · CLO)
                                  |
                can be called in at any stage, any folder
                                  |
   Opportunity → PMOS (Technical/) → EPD → DOS (Design/) → DSP
                                                    |
                            ┌───────────────────────┼───────────────────────┐
                       EOS → TDP              BOS → BTP              FOS → FTP
                            └───────────────────────┴───────────────────────┘
                                                    |
                                            DOOS → DOTP ←→ CYOS → SAP
                                                    |
                                              Production
                                  |
                    MOS (Marketing/) — can be called in parallel,
                    at any stage, for go-to-market or brand input
```

**AOS is standalone and optional.** It isn't shown in the pipeline diagram above because it doesn't require, and isn't required by, anything else in this repo. If you want an executive-level opportunity evaluation before product work begins, run AOS first (choose the For-Profit or Non-Profit edition — see `Business/README.md`) and optionally carry its ERP into PMOS or COT. If you'd rather skip straight to product definition, that's fine too — PMOS doesn't need an ERP to function.

**EOS, BOS, and FOS are alternatives, not a sequence** — pick the one(s) that fit your project. EOS covers all engineering disciplines together. BOS covers backend only, in full depth. FOS covers frontend only, in full depth. BOS + FOS can run in parallel for projects with significant complexity on both sides.

**DOOS runs after EOS, BOS, or FOS** — it takes their technical packages and produces the full infrastructure, deployment, and operations plan needed to get the system into production.

**CYOS runs alongside or after DOOS** — it receives infrastructure and application context from any upstream package and produces a comprehensive security audit, threat posture, and compliance plan. CYOS challenges and validates security decisions made by other teams — it doesn't just review what they planned.

| Prompt | Folder | Core Question | Primary Output |
| ------ | ------ | -------------- | --------------- |
| **COT** | Business/ | Can and should we execute this? | Executive Output Package (EOP) |
| **AOS** (standalone) | Business/ | Should this opportunity move forward? | Executive Recommendation Package (ERP) |
| **PMOS** | Technical/ | What should we build? | Executive Product Dossier (EPD) |
| **DOS** | Design/ | How should it look, feel, and behave? | Design Spec / Handoff Package (DSP) |
| **EOS** | Technical/ | How should it be built? | Technical Design Package (TDP) |
| **BOS** | Technical/ | How should the backend be built? | Backend Technical Package (BTP) |
| **FOS** | Technical/ | How should the frontend be built? | Frontend Technical Package (FTP) |
| **DOOS** | Technical/ | How do we deploy, operate, and protect this in production? | DevOps Technical Package (DOTP) |
| **CYOS** | Technical/ | Is this system secure, and what does it take to keep it that way? | Security Assessment Package (SAP) |
| **MOS** | Marketing/ | How do we build awareness, demand, and trust for this? | Go-to-Market Plan (GTM) or Marketing Strategy Dossier (MSD) |

If you're handing a deliverable from one prompt to another across folders (e.g. an AOS-produced ERP into PMOS, if you chose to use AOS), carry the **full** package, not a summary — the templates are built to be machine-readable by the next prompt, and summarizing strips out the structured fields the next stage depends on.

**`Personal/` is not part of this pipeline.** Both of its prompts are standalone, single-persona templates. The Assistant handles day-to-day personal use, with its own persistence system (a portable Memory Log, since it's designed to run on any AI model). The Company Briefing Generator interviews you and produces an Internal Company Briefing (ICB) — the one `Personal/` output that touches everything else, since you paste the finished ICB into every newly activated team so it knows who it works for before its first task. See `Personal/README.md` for both.

---

## Repository Structure

```
My-Entrepreneurship-Ecosystem/
├── README.md              # This directory index
├── Activation-Prompt.md    # Universal three-field prompt to activate any OS
├── Business/               # Executive oversight and opportunity advisory
│   ├── README.md
│   ├── AOS-ForProfit.md
│   ├── AOS-NonProfit.md
│   └── COT.md
├── Technical/               # Product management, engineering, and security planning
│   ├── README.md
│   ├── PMOS.md
│   ├── EOS.md
│   ├── BOS.md
│   ├── FOS.md
│   ├── DOOS.md
│   └── CYOS.md
├── Marketing/               # Go-to-market and brand strategy
│   ├── README.md
│   └── MOS.md
├── Design/                  # Design specification and handoff
│   ├── README.md
│   └── DOS.md
└── Personal/                # Personal assistance and founder utilities (standalone)
    ├── README.md
    ├── Assistant.md
    └── Company-Briefing.md
```

New prompt categories can be added as top-level folders, each with its own README.

## Versioning

This repo is versioned by branch, not by tag. Each major version of the ecosystem lives on its own branch, named for that version.

| Branch | Status |
| ------ | ------ |
| `v3` | Current |
| `v2` | Archived |

When a new version is started, it gets its own branch (e.g. `v3`) rather than overwriting `v2` in place. This keeps prior versions intact and browsable even after the ecosystem moves forward — useful since individual prompt templates (AOS, PMOS, COT, etc.) may change structurally between versions in ways that aren't backward compatible.

`main` always reflects the current version — for `v3`, that means `main` and the `v3` branch are kept in sync. If you're cloning or pulling this repo and just want the latest, `main` is fine; check out a specific version branch only if you need to reference an older one.

## License

This repository is maintained by [tekprodige](https://github.com/tekprodige). Use and adapt these prompts freely for your own projects.