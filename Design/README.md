# Design/

Design specification and handoff. This folder holds the prompt that turns a defined product into something an engineer can build pixel-for-pixel without guessing.

| Prompt | Description |
| ------ | ----------- |
| [`DOS.md`](DOS.md) | AI Design Operating System — defines how a product should look, feel, and behave |

---

## How DOS Fits

DOS sits between `Technical/PMOS.md` and `Technical/EOS.md` in the Technical → Design pipeline:

```
[Optional: AOS — standalone, see Business/] → ERP → Technical/PMOS → EPD → Design/DOS → DSP → Technical/EOS → TDP → Development
```

DOS expects to receive an EPD from `Technical/PMOS.md` as its primary input. Its output, the DSP, becomes the preferred input for `Technical/EOS.md`. `Business/COT.md` may also pull in the DSP at any point for executive review, typically via the CTO.

### Why DOS Is Separate From PMOS

`Technical/PMOS.md` decides **what** should be built and **why** — problem statements, personas, MVP scope, success metrics. It deliberately avoids implementation and visual detail.

DOS decides **how it looks, feels, and behaves** — the actual flows, screens, visual language, interaction states, and component-level detail an engineer needs to build it without guessing. If you're unsure whether something belongs in PMOS or DOS: business value and scope belong in `Technical/PMOS.md`; flows, visuals, and interaction belong here.

---

## Best Practices

### 1. Customize placeholders before activating

DOS uses bracketed placeholders. Replace all of them before pasting into a chat session — an unfilled placeholder will cause the Design Lead to ask you for it before initializing.

| Placeholder | Example |
| ----------- | ------- |
| `[PROJECT_NAME]` | Acme Analytics Platform |
| `[DESIGN_LEAD_NAME]` | Sam Okafor |
| `[*_NAME]` fields | Names for each design specialist role |

### 2. Always feed it an EPD, not a raw idea

DOS is built to design from a defined product, not to define one. If you give it a raw idea instead of an EPD from `Technical/PMOS.md`, it will likely end up making product decisions it isn't supposed to own — route through PMOS first.

### 3. Activate, then wait for the readiness report

Paste the full file into a new chat. The Design Lead initializes by introducing the team, confirming roles, submitting a readiness report, and requesting your first EPD or design challenge. Don't submit your first EPD until you see that readiness confirmation.

### 4. Don't let EOS skip this step for anything with real UI

`Technical/EOS.md` can technically start from a bare EPD, but it will explicitly flag that design detail is missing and may end up inferring flows, states, and interaction behavior rather than building from a specification. For anything with meaningful UI surface area, route through DOS first.

### 5. Carry deliverables forward, don't summarize them

If you're feeding DOS an EPD, paste the **full** EPD, not a paraphrase — Problem Statement, Target Users, Pain Points, Proposed Solution, and MVP Recommendation all inform design decisions. The same applies when handing the resulting DSP forward to `Technical/EOS.md` or up to `Business/COT.md`.

### 6. Expect — and preserve — disagreement

DOS specialists are designed to disagree on real tradeoffs — UI pushing for a richer visual treatment while Accessibility flags contrast or motion concerns, or UX proposing a flow that Interaction finds awkward to animate cleanly. That disagreement should show up explicitly in the output, not get smoothed into a single blended recommendation.

---

## Folder Structure

```
Design/
├── README.md      # This file
└── DOS.md
```

## Design Principles

- **Role continuity** — The Design Lead stays in character unless you explicitly instruct otherwise.
- **Structured deliverables** — Templates enforce consistent, reviewable outputs.
- **Explicit handoffs** — Status indicators (green / yellow / red) signal when a spec is ready for engineering.
- **Independent validation** — DOS reviews EPDs from `Technical/PMOS.md` rather than treating them as final, and documents disagreements rather than deferring to them.
- **Clear boundaries** — DOS does not redefine product scope, business value, or engineering architecture.
- **You decide** — This prompt recommends; you remain Project Owner and final decision maker.