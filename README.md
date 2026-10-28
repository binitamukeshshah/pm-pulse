# PM Pulse

**A personal AI learning system that turns high-value long-form product content into a ranked, verified, and conversational daily curriculum.**

[Product brief](PRODUCT_BRIEF.md) · [Architecture](ARCHITECTURE.md) · [Privacy and rights](PRIVACY.md)

> PM Pulse is not another summarizer. It is a workflow for deciding what is worth learning, verifying what the source actually said, delivering the right depth at the right time, and strengthening retention through dialogue.

## Why I built it

Some of the best product and strategy education lives in three-to-six-hour podcasts and continuously published subscription research. Access was not the constraint. The constraints were:

- **selection:** too much good content and no principled way to choose;
- **time:** the most valuable material is often the longest;
- **retention:** passive listening creates familiarity, not usable judgment; and
- **trust:** a confident summary is dangerous when it blurs source claims, inference, and model invention.

The existing behavior—saving episodes to an ever-growing queue—was not working. A backlog without scarcity becomes a guilt list.

PM Pulse reframes the problem from “How do I summarize more content?” to:

> **How might I build a daily learning system that improves product judgment without increasing content consumption?**

## The product insight

The highest-leverage product work happens before summarization:

1. Rank content against explicit learning goals.
2. Keep the queue intentionally scarce.
3. Preserve multiple depths instead of forcing one summary length.
4. Treat source fidelity as a release gate.
5. Deliver the reading where the habit already exists.
6. Turn follow-up questions into a durable learning artifact.

That creates a closed loop:

```text
Learning goals
     ↓
Ranked, closed curriculum
     ↓
Authorized source acquisition
     ↓
Layered guide + fidelity review
     ↓
Scheduled in-chat delivery
     ↓
Grounded conversation
     ↓
Q&A appended to the guide
     ↓
Better future ranking and recall
```

## Who it is for

PM Pulse currently serves one user: an experienced product leader preparing for senior product roles while staying current on company strategy, product craft, and applied AI.

The job to be done is:

> When valuable product content is longer than the time I have, help me identify what matters, trust the synthesis, and turn it into reasoning I can reuse in an interview or product decision.

This repository documents the workflow and product decisions. It is not a hosted multi-user application.

## What PM Pulse does

### 1. Builds a curriculum, not a backlog

Every candidate episode is scored against a configurable rubric:

| Criterion | Weight |
|---|---:|
| Interview and role relevance | 35% |
| Current learning goals and skill gaps | 25% |
| Transferability to other companies and problems | 20% |
| Target-company relevance | 10% |
| Personal interest | Tracked; not yet scored |

The queue is closed. New items must displace lower-value items instead of silently extending the backlog.

### 2. Produces the right depth for the moment

Each approved source becomes a layered guide:

- **Executive brief (~5 minutes):** crux first, organized around questions and decisions.
- **Detailed summary (~15–20 minutes):** the complete argument in source order.
- **Deep dives:** one expandable artifact per section.
- **PM lessons:** source-linked lessons mapped to explicit learning goals.
- **Knowledge card:** a one-page retrieval aid for future recall.

One summary length cannot serve a rushed morning, a focused study block, and a deep interview-prep session equally well.

### 3. Uses fidelity as a quality gate

A guide is not eligible for delivery until it passes a review that includes:

- sampled claims traced to transcript timestamps;
- quotes checked against the transcript;
- every important number re-traced to the source; and
- analytical statements labeled as **Said** (source claim) or **Read** (system inference).

If the guide is not ready, the system says so. It does not improvise a briefing from model memory to fill a delivery slot.

### 4. Delivers into the habit

The full executive brief arrives in chat on a schedule. It is not hidden behind a link that requires another decision.

The current operating rhythm uses morning and evening learning slots, with different source families assigned to different learning goals. The schedule is configurable; the underlying product principle is not: **delivery should remove friction, not add another inbox.**

### 5. Teaches through conversation

Follow-up questions are answered from that episode’s transcript and evaluated guide. Outside knowledge must be labeled rather than blended into the source.

Each exchange is appended to the guide’s Q&A log. The artifact therefore preserves both the original material and the user’s reasoning—including disagreement, clarification, and changed conclusions.

## The Muse implementation

PM Pulse uses **Muse** as the agent runtime, scheduler, delivery surface, and conversational tutor. The product work is the workflow around it:

- a source-selection policy;
- a weighted ranking model;
- a closed-queue operating rule;
- an authorized transcript-acquisition order;
- a layered guide contract;
- a fidelity evaluation gate;
- a delivery cadence; and
- a grounded Q&A memory loop.

Using an existing platform was an intentional product decision. The goal was to validate the learning experience quickly, not to rebuild scheduling, chat delivery, storage integration, and agent orchestration from scratch.

## Source strategy

PM Pulse can work with long-form company analysis, practitioner interviews, applied-AI shows, and subscription research. Current source families include:

- company-strategy podcasts;
- product-leadership and craft podcasts;
- applied-AI workflow shows; and
- subscription analysis legitimately available to the user.

Acquisition follows a strict order:

1. Official transcript published by the source.
2. User-supplied text from a legitimate subscription or account.
3. Local speech-to-text on legitimately accessible public audio.
4. Otherwise, the item is parked.

Unofficial transcript farms are not used.

## Product decisions and tradeoffs

| Decision | Chosen approach | Why |
|---|---|---|
| Build vs. integrate | Build the workflow on Muse | Faster learning validation; avoids rebuilding commodity runtime capabilities. |
| Curriculum | Closed queue | Scarcity forces prioritization and prevents backlog guilt. |
| Content depth | Layered artifacts | Supports five-minute scanning and deep study without compromise. |
| Trust model | Evaluate every guide | Hallucinated facts are the highest-cost failure mode. |
| Delivery | Full brief in chat | Links create friction and are less likely to be read. |
| Tutor grounding | Source-first, labeled inference | Prevents confident drift and preserves source integrity. |
| Storage | Plain Markdown + drive mirror | Portable, searchable, diffable, and low-lock-in. |

See [ARCHITECTURE.md](ARCHITECTURE.md) for the pipeline, data model, and failure handling.

## Validation so far

Initial pilots demonstrated the complete loop:

- a six-hour company-strategy episode was compressed into a five-minute briefing, an optional detailed guide, and a longer structured dialogue;
- a practitioner framework was studied and then applied to a different product problem in the same session; and
- sampled factual claims and quotes were rechecked before the guide entered the learning flow.

These are early, single-user signals—not proof of causal learning improvement. They validate workflow usability and source fidelity. The next validation step is longitudinal recall and transfer.

## Success metrics

The north-star is not “minutes summarized” or “episodes processed.” PM Pulse should improve usable judgment.

### Primary outcomes

- **Cold recall:** can the user reconstruct the crux days later without reopening the guide?
- **Transfer:** can the user apply the idea to a different company or product problem?
- **Decision quality:** does the learning change an interview answer or product decision?

### Product health

- guide fidelity pass rate;
- time from source selection to evaluated guide;
- delivery-to-reading conversion;
- reading-to-dialogue conversion;
- repeated-delivery rate, which should remain zero; and
- queue freshness without queue growth.

## What is public—and what is not

This repository includes:

- the product narrative;
- system architecture;
- public workflow contracts;
- an example ranking configuration; and
- artifact templates.

It deliberately excludes:

- paid or copyrighted transcripts;
- subscription research;
- generated episode guides;
- personal Q&A logs;
- provider credentials;
- private drive links; and
- the user’s detailed learning history.

## Repository structure

```text
pm-pulse/
├── README.md
├── PRODUCT_BRIEF.md
├── ARCHITECTURE.md
├── PRIVACY.md
├── LICENSE.md
├── config/
│   └── ranking-config.example.yaml
└── examples/
    ├── README.md
    └── knowledge-card-template.md
```

## Roadmap

1. Add spaced cold-recall checks several days after study.
2. Measure cross-context transfer, not just source recall.
3. Use episode-level preference data to calibrate the ranking model.
4. Create company learning arcs across multiple sources and time periods.
5. Separate workflow quality from model quality through repeatable evaluation sets.

## Status

PM Pulse is an active personal system and a product case study. The implementation runs in a private Muse workspace; this public repository documents the product thinking, operating model, and reusable workflow design without redistributing source material.

---

**If the problem is too much valuable content, the answer is not more content. It is a system that ranks, verifies, delivers, and argues with you.**
