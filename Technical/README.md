# Technical/

Product management and engineering planning. This folder picks up after an opportunity has been validated and carries it through to a build-ready technical plan.

| Prompt | Description |
| ------ | ----------- |
| [`PMOS.md`](PMOS.md) | AI Product Management Operating System — defines what should be built |
| [`EOS.md`](EOS.md) | AI Engineering Operating System — full multi-discipline engineering team |
| [`BOS.md`](BOS.md) | AI Backend Operating System — dedicated backend team for deep server-side planning |
| [`FOS.md`](FOS.md) | AI Frontend Operating System — dedicated frontend team for deep client-side planning |
| [`DOOS.md`](DOOS.md) | AI DevOps Operating System — deployment, infrastructure, and operations planning |
| [`CYOS.md`](CYOS.md) | AI Cybersecurity Operating System — security audit, threat posture, and compliance assessment |

---

## Cross-Folder Handoffs

These prompts are part of a larger pipeline that spans folders in this repo:

```
[Optional: AOS — standalone, see Business/] → ERP → PMOS → EPD → Design/DOS → DSP
                                                                         |
                                              ┌──────────────────────────┼──────────────────────────┐
                                         EOS → TDP                 BOS → BTP                 FOS → FTP
                                              └──────────────────────────┴──────────────────────────┘
                                                                         |
                                                                DOOS → DOTP → Production
```

PMOS can begin work directly from a raw idea, or optionally with an ERP from AOS — see `Business/AOS-ForProfit.md` or `Business/AOS-NonProfit.md`. PMOS hands its EPD to `Design/DOS.md`, which defines how the product should look, feel, and behave. From there, EOS (full engineering team), BOS (dedicated backend team), or FOS (dedicated frontend team) picks up for implementation planning — or BOS and FOS run in parallel for projects with significant complexity on both sides. DOOS then takes the resulting TDP, BTP, or FTP and produces the full infrastructure, deployment, and operations plan. CYOS runs alongside or after DOOS, receiving any combination of upstream packages and producing a comprehensive security audit, threat posture, and compliance assessment. `Business/COT.md` may pull in any of these deliverables at any point for executive review — see `Business/README.md`.

### EOS vs. BOS vs. FOS — Which to Use

| Use **EOS** when... | Use **BOS** when... | Use **FOS** when... |
|---------------------|---------------------|---------------------|
| You need a full multi-discipline team covering front-end, back-end, QA, full-stack, and security together | You want deep backend-only planning without a full engineering org | You want deep frontend-only planning without a full engineering org |
| The project has significant complexity across all engineering disciplines | The project is primarily backend-heavy — APIs, data, services, infra | The project is primarily frontend-heavy — components, state, animation, accessibility |
| You want a single TDP covering all engineering disciplines | You need full detail: API contracts, data models, auth, service architecture, DevOps, and full cybersecurity | You need full detail: component architecture, state management, a11y, animation, performance, and frontend security |

**BOS + FOS together:** For projects with significant complexity on both sides, run BOS and FOS in parallel using the same DSP/EPD as the shared source of truth. FOS's State & Data section should cross-reference BOS's API contracts to keep data fetching assumptions aligned.

### Why PMOS Doesn't Cover Design

PMOS decides **what** and **why** — problem statements, personas, MVP scope, success metrics. It deliberately stays out of implementation and visual detail. That work belongs to `Design/DOS.md`, which decides **how it looks, feels, and behaves** — flows, screens, visual language, interaction states, component-level detail.

---

## Best Practices

### 1. Customize placeholders before activating

All prompts in this folder use bracketed placeholders. Replace all of them before pasting into a chat session — an unfilled placeholder will cause the lead role to ask you for it before initializing.

| Placeholder | Example |
| ----------- | ------- |
| `[PROJECT_NAME]` | Acme Analytics Platform |
| `[PRODUCT_LEAD_NAME]` | Jordan Blake |
| `[TEAM_LEAD_NAME]` | Alex Rivera |
| `[BACKEND_LEAD_NAME]` | Marcus Webb |
| `[*_NAME]` fields | Names for each product, engineering, and backend specialist role |

### 2. Use one operating system per thread

Each prompt is designed to hold a single, persistent role across a conversation. Start a new thread per prompt — the same applies if you route through `Design/DOS.md` in between.

### 3. Activate, then wait for the readiness report

Paste the full file into a new chat. The lead role initializes by introducing the team, confirming roles, submitting a readiness report, and requesting your first input. Don't submit your first ERP, EPD, DSP, or feature request until you see that readiness confirmation.

### 4. Know what to submit to each

| Prompt | Submit |
| ------ | ------ |
| **PMOS** | ERPs (optional, from AOS — standalone, see `Business/`), product concepts, feature requests, strategic objectives |
| **EOS** | DSPs (from `Design/DOS.md`, preferred) or approved EPDs, product requirements, technical challenges |
| **BOS** | DSPs (from `Design/DOS.md`, preferred) or approved EPDs, feature requests, backend-specific technical challenges |
| **FOS** | DSPs (from `Design/DOS.md`, preferred) or approved EPDs, feature requests, frontend-specific technical challenges |
| **DOOS** | TDPs (from EOS), BTPs (from BOS), FTPs (from FOS), or any combination — plus direct infrastructure directives |
| **CYOS** | DOTPs (from DOOS), BTPs (from BOS), TDPs (from EOS), FTPs (from FOS), or any combination — plus direct security directives |

### 5. Don't skip Design/DOS for anything with real UI surface area

EOS, BOS, and FOS can all start from a bare EPD, but all will explicitly flag that design detail is missing. For anything with meaningful user-facing flows, route through `Design/DOS.md` first — FOS in particular depends heavily on the DSP's component inventory, interaction states, and responsive breakpoints.

### 6. Carry deliverables forward, don't summarize them

When a deliverable reaches green handoff status, paste the **full** ERP / EPD / DSP / TDP / BTP into the next session — not a paraphrase. These templates are built to be machine-readable by the next prompt; summarizing strips out the structured fields (risk registers, assumptions logs, conditions, component inventories) the next stage depends on.

### 7. Expect — and preserve — disagreement

All prompts are designed for independent judgment, not consensus. If a specialist disagrees with the rest of the team, that disagreement should show up explicitly in the output, not get smoothed over.

---

## Folder Structure

```
Technical/
├── README.md      # This file
├── PMOS.md
├── EOS.md
├── BOS.md
├── FOS.md
├── DOOS.md
└── CYOS.md
```

## Design Principles

- **Role continuity** — Leads stay in character unless you explicitly instruct otherwise.
- **Structured deliverables** — Templates enforce consistent, reviewable outputs.
- **Explicit handoffs** — Status indicators (green / yellow / red) signal when work is ready to move forward, including across folder boundaries.
- **Independent validation** — Downstream prompts review upstream findings and document disagreements.
- **Clear boundaries** — PMOS does not specify visuals; EOS, BOS, FOS, DOOS, and CYOS do not redefine product or design decisions unless explicitly asked. EOS, BOS, and FOS don't overlap — choose based on what your project needs. DOOS operates on what they produce. CYOS audits and challenges what all of them planned — it does not simply validate it.
- **You decide** — These prompts recommend; you remain Project Owner and final decision maker.