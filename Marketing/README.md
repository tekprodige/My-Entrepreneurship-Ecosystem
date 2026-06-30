# Marketing/

Go-to-market and brand strategy. This folder holds the prompt that handles audience, positioning, channel, and reputation thinking — and unlike the Business/Technical pipeline, it's designed to be called in at any stage rather than run once in sequence.

| Prompt | Description |
| ------ | ----------- |
| [`MOS.md`](MOS.md) | AI Marketing Operating System — go-to-market planning and brand/channel strategy |

---

## How MOS Fits

MOS sits parallel to the Business → Technical pipeline, the same way `Business/COT.md` does. It can be engaged before a product exists (positioning groundwork), alongside `Technical/PMOS.md` work (go-to-market planning), at launch, or post-launch (growth and retention).

MOS can take in a raw idea, an ERP if AOS was used (now standalone — see `Business/AOS-ForProfit.md` or `Business/AOS-NonProfit.md`), an EPD from `Technical/PMOS.md`, a DSP from `Design/DOS.md`, a TDP from `Technical/EOS.md`, or a standalone campaign brief. It coordinates with `Business/COT.md`, primarily through the CMO.

---

## Best Practices

### 1. Customize placeholders before activating

MOS uses bracketed placeholders. Replace all of them before pasting into a chat session — an unfilled placeholder will cause the lead role to ask you for it before initializing.

| Placeholder | Example |
| ----------- | ------- |
| `[PROJECT_NAME]` | Acme Analytics Platform |
| `[MARKETING_LEAD_NAME]` | Riley Park |
| `[*_NAME]` fields | Names for each marketing specialist role |

### 2. Know which deliverable you're asking for

MOS produces two different outputs depending on what's submitted:

| If you submit... | You'll get a... |
| ------------------ | ---------------- |
| A specific product, feature, EPD, or TDP ready for launch | **Go-to-Market Plan (GTM)** |
| A broader brand, channel, or ongoing marketing question | **Marketing Strategy Dossier (MSD)** |

If it's ambiguous, MOS will ask which you intend before proceeding — but stating it upfront ("I need a GTM for…" or "I need a strategy dossier on…") saves a round trip.

### 3. Activate, then wait for the readiness report

Paste the full file into a new chat. The Marketing Lead initializes by introducing the team, confirming roles, submitting a readiness report, and requesting your first input. Don't submit your first brief or deliverable until you see that readiness confirmation.

### 4. Carry deliverables forward, don't summarize them

If you're feeding MOS an ERP, EPD, or TDP from another folder, paste the **full** package, not a paraphrase. The templates are built to be machine-readable; summarizing strips out the structured fields (risk registers, assumptions logs) MOS depends on.

### 5. Expect — and preserve — disagreement

MOS specialists are designed to disagree on real tradeoffs — Growth pushing paid acquisition while SEO argues organic-first, or Brand prioritizing consistency while Social pushes platform-native content. That disagreement should show up explicitly in the output, not get smoothed into a single blended recommendation.

### 6. Use COT to pressure-test a launch before it goes live

Once MOS produces a GTM, consider routing it through `Business/COT.md` (the CMO) before committing budget — especially for first launches or anything with reputation exposure.

---

## Folder Structure

```
Marketing/
├── README.md      # This file
└── MOS.md
```

## Design Principles

- **Role continuity** — The Marketing Lead stays in character unless you explicitly instruct otherwise.
- **Structured deliverables** — Templates enforce consistent, reviewable outputs.
- **Explicit handoffs** — Status indicators (green / yellow / red) signal when a plan is ready to execute.
- **Independent validation** — MOS reviews findings carried over from other folders and documents disagreements rather than deferring to them.
- **You decide** — This prompt recommends; you remain Project Owner and final decision maker.