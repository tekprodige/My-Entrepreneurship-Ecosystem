# Business/

Executive oversight and opportunity advisory. This folder holds the prompts that evaluate whether an opportunity is worth pursuing and give the Founder an executive-level read on decisions at any stage.

| Prompt | Description |
| ------ | ----------- |
| [`AOS-ForProfit.md`](AOS-ForProfit.md) | AI Advisor Operating System (For-Profit) — evaluates whether a for-profit business opportunity should move forward |
| [`AOS-NonProfit.md`](AOS-NonProfit.md) | AI Advisor Operating System (Non-Profit) — evaluates whether a mission-driven program or initiative should move forward |
| [`COT.md`](COT.md) | Chief Officers Team — standing executive layer (CEO, COO, CFO, CTO, CMO, CPO, CLO) |

---

## How These Differ

**AOS** (either edition) is standalone — it doesn't sit in the Technical → Design pipeline and doesn't require anything else in this repo to function. It runs once, early, before product or engineering work begins, and produces a single deliverable (the ERP) that *can* become the strategic foundation for everything downstream, if you choose to carry it forward. It comes in two editions because a for-profit venture and a non-profit program get evaluated through genuinely different lenses — investor attractiveness and profitability don't apply to a grant-funded program, and funder/donor fit and beneficiary impact don't apply to a venture-backed startup. Pick whichever edition matches what you're evaluating; you don't need both.

**COT** is not a one-time review. It's a standing executive layer you can call into at any point — after an AOS ERP (if you used one), after a Technical/PMOS EPD, after a Design/DOS DSP, after a Technical/EOS TDP, or before a Marketing/MOS launch — whenever you want a domain-specific executive read on a decision.

AOS asks: *should this exist?* COT asks: *can and should we execute this, right now, given where it stands?*

---

## Using AOS On Its Own

Since AOS is standalone, you can use it for opportunity evaluation entirely independent of the rest of this repo — there's no requirement to feed its ERP into `Technical/PMOS.md` or anywhere else. If you do want to carry it forward, the ERP is built to be handed off in full to PMOS (which will treat it as optional context) or to COT (via the CPO) for executive review.

---

## Best Practices

### 1. Pick the right AOS edition before you start

If you're evaluating a for-profit venture, business idea, or revenue-generating opportunity, use `AOS-ForProfit.md`. If you're evaluating a non-profit program, grant-funded initiative, or mission-driven opportunity, use `AOS-NonProfit.md`. The two have different advisor rosters and different ERP fields — don't mix them mid-session.

### 2. Customize placeholders before activating

All three prompts use bracketed placeholders. Replace all of them before pasting into a chat session — an unfilled placeholder will cause the lead role to ask you for it before initializing.

| Placeholder | Example |
| ----------- | ------- |
| `[PROJECT_NAME]` / `[COMPANY_NAME]` | Acme Analytics Platform |
| `[ADVISOR_LEAD_NAME]` | Morgan Chen |
| `[CEO_NAME]`, `[CFO_NAME]`, etc. | Names for each Chief Officer |
| `[*_NAME]` fields | Names for each advisor role |

### 3. Use one operating system per thread

Each prompt is designed to hold a single, persistent role across a conversation. Running AOS and COT in the same thread blurs their boundaries. Start a new thread per prompt, and a new thread per COT session if you're running parallel executive reviews.

### 4. Activate, then wait for the readiness report

Paste the full file into a new chat. The lead role (or, for COT, the full officer roster) initializes by introducing the team, confirming roles, submitting a readiness report, and requesting your first input. Don't submit your first idea, ERP, EPD, or TDP until you see that readiness confirmation.

### 5. Know what to submit to each

| Prompt | Submit |
| ------ | ------ |
| **AOS (either edition)** | Business ideas, program concepts, startup concepts, strategic initiatives, major decisions, opportunities |
| **COT** | Decisions, AOS ERPs if one exists (via CPO), Technical/PMOS EPDs, Design/DOS DSPs, Technical/EOS TDPs, Marketing/MOS plans, execution-readiness questions, or directives to a specific officer |

### 6. Carry deliverables forward, don't summarize them

If you choose to carry an AOS ERP forward, paste the **full** ERP into the next session — not a paraphrase. The templates are built to be machine-readable by the next prompt; summarizing strips out the structured fields (risk registers, assumptions logs, conditions) the next stage depends on. The same applies when handing any deliverable to COT for review.

### 7. Use COT to pressure-test handoffs, not replace them

COT is most useful at the moments where you, the Founder, have to make a call: after an AOS ERP comes back (if you used one), after a Technical/PMOS EPD comes back, after a Design/DOS DSP comes back, after a Technical/EOS TDP comes back, or before a Marketing/MOS launch goes live. Calling individual officers (e.g. "CFO only — review this") is faster than convening the full team when you only need one domain's read.

### 8. Expect — and preserve — disagreement

All three prompts are designed for independent judgment, not consensus. If an advisor or officer disagrees with the rest of the team, that disagreement should show up explicitly in the output, not get smoothed over. Don't ask the system to "make everyone agree" — that defeats the purpose. In the Non-Profit AOS edition specifically, expect real tension between the Funder/Donor Advisors and the Beneficiary Advisor when a funding source's priorities don't match what a community actually needs — that tension is meant to surface, not get resolved away.

---

## Folder Structure

```
Business/
├── README.md      # This file
├── AOS-ForProfit.md
├── AOS-NonProfit.md
└── COT.md
```

## Design Principles

These apply across all three prompts in this category:

- **Role continuity** — Leads stay in character unless you explicitly instruct otherwise.
- **Structured deliverables** — Templates enforce consistent, reviewable outputs.
- **Explicit handoffs** — Status indicators (green / yellow / red) signal when work is ready to move forward.
- **Independent validation** — Officers and advisors review findings on their own terms and document disagreements.
- **Executive oversight, not override** — COT evaluates execution readiness; it does not redefine what AOS, Technical/PMOS, Design/DOS, or Technical/EOS already decided.
- **Standalone where it matters** — AOS doesn't assume a venture is for-profit, and doesn't assume you'll use the rest of this repo at all.
- **You decide** — These prompts recommend; you remain Project Owner and final decision maker.