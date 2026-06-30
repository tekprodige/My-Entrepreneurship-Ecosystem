# My-Entrepreneurship-Ecosystem

A personal directory of engineered AI prompts — structured system prompts, workflows, and templates built for use in LLM chat sessions (Cursor, ChatGPT, Claude, and similar tools).

This repo grows over time. Prompts are organized by category so you can browse, copy, and adapt them for your own work.

## Prompt Directory

| Category | Description | Prompts |
| -------- | ----------- | ------- |
| [**Technical/**](Technical/) | Multi-agent operating systems for advisory, product, and engineering workflows | [AOS](Technical/AOS.txt) · [PMOS](Technical/PMOS.txt) · [EOS](Technical/EOS.txt) |

*More categories and prompts will be added here as they are developed.*

---

## Technical — Operating Systems

The `Technical/` folder contains a three-stage pipeline of AI operating system prompts. Each defines a virtual organization with named roles, workflows, deliverable templates, and handoff criteria. All current templates are **Official Template v2.1**.

### The Pipeline

These operating systems are designed to run in sequence. Each stage answers a different question and produces a specific deliverable for the next.

```
Opportunity → AOS → ERP → PMOS → EPD → EOS → TDP → Development
```

| Stage | Operating System | Core Question | Primary Output |
| ----- | ---------------- | ------------- | -------------- |
| 1 | **AOS** — AI Advisor Operating System | Should this opportunity move forward? | Executive Recommendation Package (ERP) |
| 2 | **PMOS** — AI Product Management Operating System | What should we build? | Executive Product Dossier (EPD) |
| 3 | **EOS** — AI Engineering Operating System | How should it be built? | Technical Design Package (TDP) |

Each organization has a clear boundary. Advisors do not define products. Product does not design architecture. Engineering does not validate market fit. That separation keeps reviews focused and outputs consistent.

### AOS — AI Advisor Operating System

[`Technical/AOS.txt`](Technical/AOS.txt)

The Advisor Organization evaluates opportunities **before** product discovery and engineering planning. Its job is critical analysis, not encouragement — identifying weaknesses, blind spots, risks, missing information, and strategic, operational, financial, and reputation concerns.

**Advisor Lead** coordinates the team. **Advisors** include Business, Financial, Investor, Risk, Legal, Industry, and PR & Communications specialists, each with a defined evaluation lens.

**Output:** Executive Recommendation Package (ERP) with handoff status (Ready for PMOS / Needs Additional Research / Not Ready).

### PMOS — AI Product Management Operating System

[`Technical/PMOS.txt`](Technical/PMOS.txt)

The Product Organization runs **after** strategic review and **before** engineering planning. It transforms opportunities, executive directives, and ERPs into validated product recommendations.

**Product Lead** coordinates discovery, research, validation, and MVP definition. The team evaluates every recommendation through five lenses: User Value, Business Value, Market Value, Operational Value, and Risk Profile.

**Output:** Executive Product Dossier (EPD) with advisor feedback review, revision history, and an Engineering Handoff Section.

### EOS — AI Engineering Operating System

[`Technical/EOS.txt`](Technical/EOS.txt)

The Engineering Organization transforms approved product requirements into implementation-ready technical plans. It does not redefine product strategy or perform market validation unless explicitly requested.

**Team Lead** oversees architecture, planning, and delivery. **Engineering team members** include Front-End, Back-End, QA, Full-Stack, and Security engineers, each operating in dedicated Team Threads.

**Output:** Technical Design Package (TDP) with handoff status (Ready for Development / Requires Clarification / Not Ready).

### Using the Operating Systems

**1. Customize placeholders** — Replace bracketed values before pasting into a chat session:

| Placeholder | Example |
| ----------- | ------- |
| `[PROJECT_NAME]` | Acme Analytics Platform |
| `[ADVISOR_LEAD_NAME]` | Morgan Chen |
| `[PRODUCT_LEAD_NAME]` | Jordan Blake |
| `[TEAM_LEAD_NAME]` | Alex Rivera |
| `[*_NAME]` fields | Names for each advisor, product, and engineering role |

**2. Activate** — Copy the full `.txt` file into a new chat. The lead role initializes by introducing the team, confirming roles, submitting a readiness report, and requesting your first input.

**3. Provide input**

| OS | Submit |
| -- | ------ |
| **AOS** | Business ideas, startup concepts, strategic initiatives, major decisions, opportunities |
| **PMOS** | ERPs, product concepts, feature requests, strategic objectives |
| **EOS** | Approved EPDs, product requirements, feature requests, technical challenges |

**4. Hand off** — When an output reaches green handoff status, carry the deliverable (ERP → EPD → TDP) into the next operating system's session.

---

## Repository Structure

```
My-Engineered-Prompts/
├── README.md              # This directory index
└── Technical/             # Advisory, product, and engineering operating systems
    ├── AOS.txt
    ├── PMOS.txt
    └── EOS.txt
```

New prompt categories can be added as top-level folders alongside `Technical/`.

## Design Principles

These apply across prompts in this repo, starting with the operating systems:

- **Role continuity** — Leads stay in character unless you explicitly instruct otherwise.
- **Structured deliverables** — Templates enforce consistent, reviewable outputs.
- **Explicit handoffs** — Status indicators (green / yellow / red) signal when work is ready to move forward.
- **Independent validation** — Downstream prompts review upstream findings and document disagreements.
- **You decide** — AI organizations recommend; you remain Project Owner and final decision maker.

## License

This repository is maintained by [tekprodige](https://github.com/tekprodige). Use and adapt these prompts freely for your own projects.
