# PM Pulse: Product Brief

## Executive summary

PM Pulse is a personal AI learning system for an experienced product leader. It converts long-form product and strategy content into a scarce, trusted daily curriculum, then turns passive consumption into active reasoning through source-grounded conversation.

The implementation uses Muse as the runtime. The differentiated product value is the workflow layered on top: ranking, closed-queue discipline, depth-based artifacts, fidelity evaluation, scheduled delivery, and append-only conversational learning.

## User and context

**Primary user:** a senior product leader preparing for high-scope PM roles while staying current on company strategy, product craft, and applied AI.

**Context:** the user has access to high-quality content but cannot consume it at publication speed. Long episodes compete with interview preparation, career work, and a full daily schedule.

**Current alternatives:** podcast queues, saved links, generic AI summaries, notes apps, and ad hoc chats.

## Job to be done

> When valuable product content is longer than the time I have, help me decide what is worth learning, trust the synthesis, and turn it into reasoning I can reuse.

## User problems

| Problem | Existing behavior | Consequence |
|---|---|---|
| Content abundance | Save everything | Infinite backlog and weak prioritization |
| Long duration | Listen opportunistically | Inconsistent progress and high time cost |
| Passive consumption | Finish and move on | Low recall and little transfer |
| Summary mistrust | Accept fluent output | Source claims and inference become blurred |
| Fragmented learning | Ask isolated follow-ups | Insight disappears with the chat session |

## Product hypothesis

If the system ranks content against explicit learning goals, provides a verified layered guide, and captures grounded dialogue back into the learning artifact, then the user will retain and transfer more product judgment per hour than through passive listening or generic summarization.

## Value proposition

### Functional

- Spend learning time on the highest-value source.
- Reach the crux in minutes while preserving optional depth.
- Trust that important claims were checked.
- Reuse prior dialogue instead of restarting.

### Emotional

- Replace backlog guilt with a bounded curriculum.
- Reduce anxiety that important content is being missed.
- Build confidence grounded in understanding, not surface familiarity.

### Career

- Strengthen product strategy, prioritization, and executive compression.
- Build richer company and industry mental models.
- Practice transferring frameworks to unfamiliar problems.

## MVP scope

The MVP deliberately serves one user and proves one learning loop:

1. Curate and rank source candidates.
2. Acquire an authorized transcript.
3. Generate layered guide artifacts.
4. Run a fidelity review.
5. Deliver the executive brief in chat.
6. Support transcript-grounded Q&A.
7. Append the discussion to the guide.

## Non-goals

- Becoming a general-purpose podcast application.
- Maximizing content throughput.
- Redistributing transcripts or subscription content.
- Replacing source creators.
- Claiming learning improvement from summary volume alone.
- Building commodity agent infrastructure already provided by Muse.

## Product principles

1. **Crux first.** The first lines must carry the central idea.
2. **Scarcity improves ranking.** New items displace; they do not accumulate.
3. **Depth is pull-based.** The default is concise, while detail remains available.
4. **Trust is a feature.** A guide does not ship before fidelity review.
5. **Inference must be visible.** Said and Read are separate.
6. **Delivery belongs in the habit.** The brief arrives where learning already happens.
7. **Dialogue creates retention.** Conversation is part of the artifact, not a disposable layer.

## Key product risks

| Risk | Mitigation |
|---|---|
| Fluent but inaccurate synthesis | Mandatory claim, quote, and number checks |
| Queue becomes another backlog | Closed-list replacement rule |
| Delivery becomes notification noise | Fixed slots and a strict content budget |
| User reads but does not retain | Cold recall and cross-context transfer tests |
| Tutor drifts beyond the source | Transcript grounding and labeled outside knowledge |
| Rights or privacy leakage | Private source library; public repository contains workflow only |

## Measurement plan

### Learning outcomes

- unaided crux recall after 3–7 days;
- ability to explain the underlying causal model;
- successful application to a novel company or product scenario; and
- evidence that the insight changed an answer or decision.

### Funnel

```text
Ranked → Built → Evaluation passed → Delivered → Read → Discussed → Recalled → Transferred
```

Each conversion reveals a different failure mode. High build volume with low discussion is not product success.

## Why this is a product-management project

PM Pulse demonstrates a build-versus-integrate decision, explicit user/problem framing, prioritization under scarcity, workflow design, quality gates, feedback loops, and outcome-oriented measurement. The implementation matters, but the product is the operating model around the tools.
