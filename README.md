# My-Entrepreneurship-Ecosystem

An interconnected ecosystem of AI prompts for running a venture end to end — from initial opportunity evaluation through executive oversight, product definition, design, engineering, marketing, and day-to-day personal support. Each prompt is a structured system prompt built for use in LLM chat sessions (Cursor, ChatGPT, Claude, and similar tools), and several are designed to hand off deliverables to one another.

This repo grows over time. Prompts are organized by category so you can browse, copy, and adapt them for your own work.

## Prompt Directory

| Category | Description | Prompts |
| -------- | ----------- | ------- |
| [**Business/**](Business/) | Executive oversight and opportunity advisory | [AOS — For-Profit](Business/AOS-ForProfit.md) · [AOS — Non-Profit](Business/AOS-NonProfit.md) · [COT](Business/COT.md) |
| [**Technical/**](Technical/) | Product management and engineering planning | [PMOS](Technical/PMOS.md) · [EOS](Technical/EOS.md) · [BOS](Technical/BOS.md) · [FOS](Technical/FOS.md) |
| [**Marketing/**](Marketing/) | Go-to-market and brand strategy | [MOS](Marketing/MOS.md) |
| [**Design/**](Design/) | Design specification and handoff | [DOS](Design/DOS.md) |
| [**Personal/**](Personal/) | Personal, day-to-day assistance (standalone) | [Assistant](Personal/Assistant.md) |

*More categories and prompts will be added here as they are developed.*

Each category folder has its own README with prompt-specific best practices, structure, and design principles. Start there once you've picked a category.

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
                                              Development
                                  |
                    MOS (Marketing/) — can be called in parallel,
                    at any stage, for go-to-market or brand input
```

**AOS is standalone and optional.** It isn't shown in the pipeline diagram above because it doesn't require, and isn't required by, anything else in this repo. If you want an executive-level opportunity evaluation before product work begins, run AOS first (choose the For-Profit or Non-Profit edition — see `Business/README.md`) and optionally carry its ERP into PMOS or COT. If you'd rather skip straight to product definition, that's fine too — PMOS doesn't need an ERP to function.

**EOS, BOS, and FOS are alternatives, not a sequence** — pick the one(s) that fit your project. EOS covers all engineering disciplines together. BOS covers backend only, in full depth. FOS covers frontend only, in full depth. BOS + FOS can run in parallel for projects with significant complexity on both sides.

| Prompt | Folder | Core Question | Primary Output |
| ------ | ------ | -------------- | --------------- |
| **COT** | Business/ | Can and should we execute this? | Executive Output Package (EOP) |
| **AOS** (standalone) | Business/ | Should this opportunity move forward? | Executive Recommendation Package (ERP) |
| **PMOS** | Technical/ | What should we build? | Executive Product Dossier (EPD) |
| **DOS** | Design/ | How should it look, feel, and behave? | Design Spec / Handoff Package (DSP) |
| **EOS** | Technical/ | How should it be built? | Technical Design Package (TDP) |
| **BOS** | Technical/ | How should the backend be built? | Backend Technical Package (BTP) |
| **FOS** | Technical/ | How should the frontend be built? | Frontend Technical Package (FTP) |
| **MOS** | Marketing/ | How do we build awareness, demand, and trust for this? | Go-to-Market Plan (GTM) or Marketing Strategy Dossier (MSD) |

If you're handing a deliverable from one prompt to another across folders (e.g. an AOS-produced ERP into PMOS, if you chose to use AOS), carry the **full** package, not a summary — the templates are built to be machine-readable by the next prompt, and summarizing strips out the structured fields the next stage depends on.

**`Personal/` is not part of this pipeline.** The Assistant prompt is a standalone, single-persona template for day-to-day personal use — it doesn't hand off to or receive from any of the prompts above. See `Personal/README.md` for how it works, including its own persistence system (a portable Memory Log, since it's designed to run on any AI model).

---

## Repository Structure

```
My-Entrepreneurship-Ecosystem/
├── README.md              # This directory index
├── Business/               # Executive oversight and opportunity advisory
│   ├── README.md
│   ├── AOS-ForProfit.md
│   ├── AOS-NonProfit.md
│   └── COT.md
├── Technical/               # Product management and engineering planning
│   ├── README.md
│   ├── PMOS.md
│   ├── EOS.md
│   ├── BOS.md
│   └── FOS.md
├── Marketing/               # Go-to-market and brand strategy
│   ├── README.md
│   └── MOS.md
├── Design/                  # Design specification and handoff
│   ├── README.md
│   └── DOS.md
└── Personal/                # Personal, day-to-day assistance (standalone)
    ├── README.md
    └── Assistant.md
```

New prompt categories can be added as top-level folders, each with its own README.

## Versioning

This repo is versioned by branch, not by tag. Each major version of the ecosystem lives on its own branch, named for that version.

| Branch | Status |
| ------ | ------ |
| `v2` | Current |

When a new version is started, it gets its own branch (e.g. `v3`) rather than overwriting `v2` in place. This keeps prior versions intact and browsable even after the ecosystem moves forward — useful since individual prompt templates (AOS, PMOS, COT, etc.) may change structurally between versions in ways that aren't backward compatible.

`main` always reflects the current version — for `v2`, that means `main` and the `v2` branch are kept in sync. If you're cloning or pulling this repo and just want the latest, `main` is fine; check out a specific version branch only if you need to reference an older one.

## License

This repository is maintained by [tekprodige](https://github.com/tekprodige). Use and adapt these prompts freely for your own projects.