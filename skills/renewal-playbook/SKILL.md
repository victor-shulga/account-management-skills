---
name: renewal-playbook
description: >-
  Builds the renewal motion for a B2B service company: a renewal calendar with a 60-day
  trigger, a renewal-risk read per account, the play to run at T-60, T-30 and T-7, save plays
  for accounts at risk, and the rate-increase conversation for long-standing clients. Output is
  a tracker plus a per-account action list. Use when the user says "план продовжень", "renewal
  playbook", "трекер продовжень", "кого продовжуємо", "контракт закінчується", "клієнт не
  продовжив, що робимо", "підвищення ставки", "rate increase", "хто в зоні ризику на
  продовження", or hands a list of accounts with end dates. NOT for scoring general account
  health (client-health-check; this skill consumes its output), NOT for cross-sell mapping
  (upsell-mapper), NOT for winning back a client who already left (reply-objection-handler).
---

# Renewal Playbook

In a service business a renewal is the moment the client re-decides, whatever the contract
date says. This skill makes that decision visible 60 days early and gives the account owner
something to do about it.

## What it produces

1. **Renewal tracker**: one row per active account, sorted by renewal date.
2. **Risk read**: green / yellow / red per account, with the evidence.
3. **Play per account**: what happens at T-60, T-30, T-7, and what happens if they say no.

Write the output in the user's language. In Ukrainian use plain words (продовження, ОПР,
розширення), no anglicisms.

---

## Tracker columns

| Column | Rule |
| :-- | :-- |
| Client | name or anonymised label |
| Service line | which service is up for renewal |
| Current value | monthly or project value |
| End date | contract end, or the natural end of the current scope |
| T-60 date | end date minus 60 days; this is the reminder that must fire |
| Health | score from `client-health-check` |
| Renewal risk | 🟢 / 🟡 / 🔴 (see below) |
| Risk reason | one line, from facts |
| Owner | who runs the renewal |
| Play | which play runs |
| Status | not started · in conversation · renewed · expanded · lost |

Rolling engagements without a formal end date still get a row: use the natural review point
(quarter end, phase end). An engagement nobody re-decides is the one that quietly stops.

## Risk read: 5 signals

Score each: 🟢 healthy · 🟡 watch · 🔴 danger. **The worst signal wins.** Do not average.

| # | Signal | 🔴 looks like |
| :-- | :-- | :-- |
| 1 | Scope of work | scope shrinking for 2+ months, or a phase ending with nothing planned after it |
| 2 | Access to the economic buyer | the buyer changed, went quiet, or was never met |
| 3 | Visible results | the client cannot name what they got; no quarterly review ever ran |
| 4 | Tone and response speed | short, delayed, delegated downward |
| 5 | External signals | hiring the role in-house, budget freeze, a new competitor on site, M&A |

Silence is a stronger churn signal than a late invoice. An account can be red with perfect payments.

---

## The plays

### T-60: a conversation about the next period, not about a signature
Run the quarterly review (`qbr-builder`, pack `account-management-skills`, if installed; otherwise a meeting that covers results in their numbers, what did not work, and the next quarter) if one is not already scheduled. The renewal comes out
of a good review; it is never its own agenda item. Leave with three things: what the next
period looks like, what they want changed, who signs.

### T-30: lock the scope
Written scope and price for the next period, drafted by you and sent by the client-facing owner.
If T-60 surfaced a red signal, the save play runs here instead.

### T-7: confirmation
Short, no new information. If nothing is confirmed by T-7, treat it as red and escalate to the
economic buyer directly. Another email to the day-to-day contact does not count as escalation.

### Save plays (run at the first red, not at T-7)

| Risk reason | Play |
| :-- | :-- |
| Results are not visible | value recap in their numbers + an immediate quarterly review; show before and after, not activity |
| Economic buyer changed or unreachable | re-introduction meeting with the new buyer; treat it as a new sale and re-qualify (`scope-qualifier`, pack `sales-engine-skills`, if installed) |
| Scope is ending naturally | bring the next phase (from `upsell-mapper`, if installed) BEFORE the current one ends |
| They are moving it in-house | reframe to the capability gap: what stays hard in-house (ramp time, peak load, a niche skill). Offer a hybrid instead of defending the whole scope |
| Budget frozen | offer a smaller retained scope that keeps the relationship warm, with a written restart trigger |
| Unhappy with quality | escalation recovery: own it, name the cause, name the fix with a date, put a checkpoint in 2 weeks. A discount is never the first move |

### Rate increase (clients of 2+ years)

Run it as a separate conversation, 90 days before renewal, never bundled into the renewal ask.
Structure: what changed on your side (scope, seniority, cost base), then what they got this year
in their numbers, then the new rate with the effective date, then what stays the same. One
number, no menu. If the account is 🔴 on health, fix the health first; a raise on a shaky
account usually ends in churn.

---

## Process

1. Collect active accounts with dates, values and service lines. Missing end dates: set review points.
2. Pull `client-health-check` scores (pack `account-management-skills`, if installed). Do not
   re-derive them here. If the skill is not installed, ask the user for a health read per account
   and mark it as self-reported.
3. Score the 5 renewal signals per account. Every 🔴 or 🟡 carries its evidence in the row.
4. Build the tracker, sorted by date. Set the T-60 reminder mechanism explicitly (calendar,
   CRM task, scheduled reminder). A tracker that reminds nobody does nothing.
5. Assign the play per account, with an owner and the T-60 date.
6. Output the top 3 accounts at risk with the single next action for each.
7. Save the tracker where the team works: a Notion database or page if the Notion connector is
   available, otherwise a markdown table or CSV file the user can paste into their CRM or sheet.

## Rules

- Facts only. A risk flag without evidence in the row is noise.
- You draft; the client-facing owner sends and speaks. Never send outreach on someone's behalf.
- Renewal and expansion are separate moves. Do not stack an upsell onto a red account: save
  first, grow after.
- Definition of done: every active account is in the tracker, and the 60-day reminder fires.

## Credits

Method by Victor Shulga (victorshulga.com).
