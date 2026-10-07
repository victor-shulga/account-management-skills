---
name: cs-plan-builder
description: >-
  Builds the customer success plan for a B2B service account: the written agreement on what
  "working" means. Covers the client's own success criteria, the checkpoint rhythm, the
  stakeholder map with the risk of each person, the early-warning signals, and the feedback loop
  that turns what clients say into revenue decisions (expansion, retention, service line,
  pricing). Two modes: PLAN (per account) and FEEDBACK (turn a batch of client feedback or NPS
  answers into a decision list). Use when the user says "план успіху клієнта", "customer success
  plan", "success criteria", "як ми домовляємось про результат", "стейкхолдер-мапа акаунту",
  "NPS", "зібрали фідбек, що з ним робити", "чому клієнти йдуть", "перетвори відгуки на
  рішення". NOT for scoring account health (client-health-check; this skill consumes it), NOT
  for the quarterly review meeting (qbr-builder), NOT for the handoff at project start.
---

# CS Plan Builder

Retention is the thinnest block in most agency go-to-market systems, and it fails the same way
every time: nobody wrote down what "working" means, so the client decides alone, quietly, at renewal.

Two modes. Ask which; default to `PLAN`.

Write the output in the user's language. In Ukrainian use plain words: критерії успіху,
перевірка, продовження, розширення, no anglicisms.

---

# Mode PLAN: the success plan per account

## What it produces

A one-page agreement, confirmed on a call, that answers four things: what success is, how we
will know, who cares, and what we do when it slips.

### 1. Success criteria, in the client's words

3 to 5 criteria. Each: what changes · how it is measured · who confirms it · by when.

- Written from what the client said at kick-off or the last review, in their vocabulary. The
  contract wording is a fallback, not the source.
- Each criterion must be checkable by someone other than you. "The client is happy" is not a criterion.
- Mix leading and lagging measures: a plan made only of lagging outcomes gives you nothing to
  steer with for three months.
- If the client cannot name a criterion, that IS the finding. Write "criterion not agreed" and
  make agreeing it the first checkpoint. Do not invent one to fill the row.

### 2. Stakeholder map

| Person | Role in the decision | What they need from us | Risk if they leave | Last real contact |
| :-- | :-- | :-- | :-- | :-- |

- Minimum: the economic buyer (who pays), the day-to-day contact (who works with you), the end
  user of the result (who feels it).
- Single-threaded accounts (one contact only) are the most common preventable churn. Flag it as
  a risk with a named action, not as an observation.
- "Last real contact" means a conversation. A status email does not count.

### 3. Checkpoint rhythm

| Rhythm | What happens | Who |
| :-- | :-- | :-- |
| Weekly | delivery status, blockers | PM and day-to-day contact |
| Monthly | criteria check: on track or slipping, with numbers | account manager and day-to-day contact |
| Quarterly | quarterly review (`qbr-builder`, if installed) | account manager and economic buyer |

The monthly criteria check is the one that gets skipped, and it is the one that prevents
surprises. Pick a date, name an owner, put it in the calendar as part of the definition of done.

### 4. Early signals and what we do

Signal, owner, action, deadline. Minimum four:

| Signal | Action |
| :-- | :-- |
| A criterion slipped two months in a row | escalate to the economic buyer with a cause and a fix (an apology alone is not a fix) |
| The economic buyer has been silent 6+ weeks | a direct meeting request, asked for by their own side of the table |
| Scope is shrinking | bring the next phase forward (from `upsell-mapper`, if installed) before the current one closes |
| The decision maker changed | treat it as a new sale: re-qualify (`scope-qualifier`, pack `sales-engine-skills`, if installed) and re-agree the criteria |

### 5. What we need from the client

Explicit: access, data, decisions, review turnaround. Most "agency underperformance" is a client
input that never arrived. Writing it down early is what makes that conversation possible later.

---

# Mode FEEDBACK: client feedback into revenue decisions

A feedback summary on its own leads nowhere. Every item exits as a decision or a discard,
with an owner.

## Process

1. **Collect the raw material**: review calls, NPS answers, quarterly review notes, complaints,
   churn reasons, lost-deal reasons. Quote verbatim; never paraphrase into corporate tone.
2. **Classify each item on two axes:**
   - *About what*: service · process and communication · people · price · expectations (what was sold differs from what was delivered)
   - *What to do*: fix · explain · sell (an unmet need is an expansion) · reject
3. **Root cause, not symptom.** "They are slow to reply" is a symptom; the cause is capacity,
   routing, or a response time nobody agreed, and each has a different fix. Classify to the cause.
4. **Count.** One angry client is a story; the same complaint from four is a process defect. Say
   which of the two you are looking at, with the count.
5. **Revenue read**: for each cluster, which accounts it touches, what revenue sits behind them,
   and whether it threatens renewal or blocks expansion.
6. **Decision list**: action · owner · date · which account is told about it. Closing the loop
   with the client who complained is where retention actually comes from.
7. **Expansion candidates** found in feedback go to `upsell-mapper` (if installed) with the quote
   attached. A client's own words are the strongest reason an expansion can carry. Strong
   positive quotes with numbers are raw material for `case-study-writer` (if installed), with
   the client's permission.

## NPS: use it properly or do not run it

The score alone is decoration. What matters is the **follow-up question** ("what would have to
happen for this to be a 9?") and a human answering every detractor within 48 hours. If nobody
will do the follow-up, do not send the survey: an ignored survey costs more trust than no
survey. Never publish a score built on a handful of responses as a company metric.

---

## Inputs from other skills (optional)

- Account health from `client-health-check` (pack `account-management-skills`). If it is not
  installed, ask the account owner for a short health read and label it self-reported.
- Expansion options from `upsell-mapper` (same pack).
- Quarterly review from `qbr-builder` (same pack).

## Rules (both modes)

- Facts and quotes only. Never invent a criterion, a stakeholder's motive or a feedback theme.
- You write; the client-facing people speak and send.
- If `anticopywriting-ai` (pack `gtm-skills`) is installed, run the prose through it.
- Save the plan as a Notion page under the client's page if the Notion connector is available;
  otherwise as a markdown file `<client>-success-plan.md` (or `<client>-feedback-<date>.md` in
  FEEDBACK mode).
- Definition of done, PLAN mode: criteria agreed on a call with the economic buyer, the monthly
  check dated, every signal assigned an owner. Until the economic buyer has agreed to it, the plan is only a document.

## Credits

Method by Victor Shulga (victorshulga.com).
