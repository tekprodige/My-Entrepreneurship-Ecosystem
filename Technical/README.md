# Technical/

Product management and engineering planning. This folder picks up after an opportunity has been validated and carries it through to a build-ready technical plan.

| Prompt | Description |
| ------ | ----------- |
| [`PMOS.md`](PMOS.md) | AI Product Management Operating System — defines what should be built |
| [`EOS.md`](EOS.md) | AI Engineering Operating System — defines how it should be built |

---

## Cross-Folder Handoffs

These two prompts are part of a larger pipeline that spans folders in this repo:

```
[Optional: AOS — standalone, see Business/] → ERP → PMOS → EPD → Design/DOS → DSP → EOS → TDP → Development
```

PMOS can begin work directly from a raw idea, or optionally with an ERP from AOS, which is now a standalone prompt — see `Business/AOS-ForProfit.md` or `Business/AOS-NonProfit.md`. PMOS hands its EPD to `Design/DOS.md`, which defines how the product should look, feel, and behave. EOS expects to receive a DSP from `Design/DOS.md` as its preferred input (an EPD alone is usable but lacks design-level detail). `Business/COT.md` may also pull in any of these deliverables at any point for executive review — see `Business/README.md` for that relationship.

### Why PMOS Doesn't Cover Design

PMOS decides **what** and **why** — problem statements, personas, MVP scope, success metrics. It deliberately stays out of implementation and visual detail. That work belongs to `Design/DOS.md`, which decides **how it looks, feels, and behaves** — flows, screens, visual language, interaction states, component-level detail. If you're unsure whether something belongs in PMOS or DOS: business value and scope belong here; flows, visuals, and interaction belong in `Design/`.

---

## Best Practices

### 1. Customize placeholders before activating

Both prompts use bracketed placeholders. Replace all of them before pasting into a chat session — an unfilled placeholder will cause the lead role to ask you for it before initializing.

| Placeholder | Example |
| ----------- | ------- |
| `[PROJECT_NAME]` | Acme Analytics Platform |
| `[PRODUCT_LEAD_NAME]` | Jordan Blake |
| `[TEAM_LEAD_NAME]` | Alex Rivera |
| `[*_NAME]` fields | Names for each product and engineering role |

### 2. Use one operating system per thread

Each prompt is designed to hold a single, persistent role across a conversation. Running PMOS and EOS in the same thread blurs their boundaries and weakens the independence of each review. Start a new thread per prompt — the same applies if you route through `Design/DOS.md` in between.

### 3. Activate, then wait for the readiness report

Paste the full file into a new chat. The lead role initializes by introducing the team, confirming roles, submitting a readiness report, and requesting your first input. Don't submit your first ERP, EPD, DSP, or feature request until you see that readiness confirmation.

### 4. Know what to submit to each

| Prompt | Submit |
| ------ | ------ |
| **PMOS** | ERPs (optional, from AOS — standalone, see `Business/`), product concepts, feature requests, strategic objectives |
| **EOS** | DSPs (from `Design/DOS.md`, preferred) or approved EPDs, product requirements, technical challenges |

### 5. Don't skip Design/DOS just because EOS will accept an EPD alone

EOS can technically start from a bare EPD, but it will explicitly flag that design detail is missing and may end up inferring flows, states, and interaction behavior rather than building from a specification. For anything with real UI surface area, route through `Design/DOS.md` first.

### 6. Carry deliverables forward, don't summarize them

When a deliverable reaches green handoff status, paste the **full** ERP / EPD / DSP / TDP into the next session — not a paraphrase, and not a summary, even across folders. These templates are built to be machine-readable by the next prompt; summarizing strips out the structured fields (risk registers, assumptions logs, conditions, component inventories) that the next stage depends on.

### 7. Expect — and preserve — disagreement

Both prompts are designed for independent judgment, not consensus. If a team member disagrees with the rest of the team — including disagreeing with findings carried over from an AOS ERP (if one was used) or from `Design/DOS.md` — that disagreement should show up explicitly in the output, not get smoothed over.

---

## Folder Structure

```
Technical/
├── README.md      # This file
├── PMOS.md
└── EOS.md
```

## Design Principles

These apply across both prompts in this category:

- **Role continuity** — Leads stay in character unless you explicitly instruct otherwise.
- **Structured deliverables** — Templates enforce consistent, reviewable outputs.
- **Explicit handoffs** — Status indicators (green / yellow / red) signal when work is ready to move forward, including across folder boundaries.
- **Independent validation** — Downstream prompts review upstream findings (including from an AOS ERP, if used, and from `Design/DOS.md`) and document disagreements.
- **Clear boundaries** — PMOS does not specify visuals; EOS does not redefine product or design decisions unless explicitly asked.
- **You decide** — These prompts recommend; you remain Project Owner and final decision maker.