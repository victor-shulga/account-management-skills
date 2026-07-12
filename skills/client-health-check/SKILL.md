---
name: client-health-check
description: >
  Scores every active client account green / yellow / red on 6 health criteria and
  outputs a health table + action plan for the reds. Built for B2B service companies
  (agencies, outsourcing, consulting) where losing one account hurts. Use when the user
  says: "оцінка здоров'я клієнтів", "client health check", "health scoring", "хто з
  клієнтів у зоні ризику", "churn risk review", "проскор акаунти", or pastes a list of
  active clients and asks which ones are at risk. NOT for scoring new leads
  (use lead scoring) and NOT for upsell mapping (use upsell-mapper).
---

# Client Health Check

## What it produces

A health table (one row per active client) + an action list for every yellow/red
account, ready to paste into the client's task tracker or CRM.

## The 6 criteria (score each 0–2)

| # | Criterion | 2 (green) | 1 (yellow) | 0 (red) |
|---|---|---|---|---|
| 1 | Work volume trend | growing or stable | slight decline | shrinking 2+ months |
| 2 | Payment behavior | on time | occasional delays | overdue / disputes |
| 3 | Communication tone | engaged, proactive | neutral, reactive only | cold, short, or silent |
| 4 | Decision-maker access | regular contact with the economic buyer | only day-to-day contacts | buyer changed / unreachable |
| 5 | Result visibility | client sees and confirms value | value delivered but not shown | client questions the value |
| 6 | Expansion signals | asks about more scope | none | mentions competitors / budget cuts |

**Total: 10–12 = green · 6–9 = yellow · 0–5 = red.**

## Process

1. Ask for the list of active clients (or pull from CRM if an MCP connection exists).
2. For each client, ask only for the facts the user can answer fast — or infer from
   provided materials (email threads, invoices, meeting notes). Never guess a score:
   if a criterion is unknown, mark it `?` and score conservatively (count as 1).
3. Output the health table sorted worst-first.
4. For every red and yellow account, add 1–3 concrete actions with an owner and a date:
   - red on tone/access → schedule a direct call with the decision-maker this week
   - red on result visibility → send a value recap: what was done, in their numbers
   - yellow on volume → check with delivery: is scope naturally ending or drifting away?
5. Recommend the review rhythm: monthly rescoring, compare with last month's table.

## Rules

- Scores come from facts the user gives, not vibes. Note the evidence in the table.
- A client can be red with perfect payments — silence is a stronger churn signal
  than a late invoice.
- The output ends with the single most urgent account and its next action.
