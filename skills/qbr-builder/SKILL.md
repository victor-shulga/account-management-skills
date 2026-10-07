---
name: qbr-builder
description: >-
  Builds the quarterly review artifact for a client account or for a board: a result-first
  narrative page (or deck) with plan and fact inside the funnel table, value shown in the
  client's money or time, expansion asks pulled from the cross-sell map, and a next-quarter plan
  with owners and dates. Two modes: QBR (one client account, run by account management) and
  BOARD (one company's whole revenue engine, prepared for its board or founder). Use when the
  user says "збери QBR", "квартальний огляд по [клієнт]", "QBR для топ-акаунту", "борд-дека",
  "board pack", "квартальний рекап", "підготуй квартальний звіт клієнту", "review for the
  board", or hands quarter numbers and asks for the review artifact. NOT the weekly outreach
  report (weekly-outreach-report), NOT the pre-call brief for a booked discovery call
  (meeting-prep), NOT account health scoring on its own (client-health-check).
---

# QBR Builder: quarterly review and board pack

Two artifacts, one engine. Both answer the same question: **what did the last quarter buy,
and what is the bet for the next one.**

| Mode | Audience | Runs on | Owner |
| :-- | :-- | :-- | :-- |
| `QBR` | ONE client account, their decision maker | delivery and revenue data for that account | account manager |
| `BOARD` | the company's board or founder | the whole revenue engine, all channels | CEO with whoever runs revenue |

Ask which mode if it is not obvious. Default to `QBR`.

---

## Hard rules

1. **Plan and fact live inside the tables.** Every metric row carries
   `Metric · Plan · Actual · % of plan`. A reader sees the deviation without scrolling. A board
   pack with actuals only is unfinished.
2. **No plan on file, no invented plan.** If the account has no agreed target, write "there was
   no plan for this quarter; we are fixing the baseline for the next one" and build the
   baseline. Never backfill a target to make the quarter look on track.
3. **Two plan sources conflict: name both**, use the one the audience has seen, and flag the
   gap. Never average them.
4. **Value in the client's units.** Money saved, hours returned, deadlines held, risk removed.
   "We ran 47 calls" is activity. If you cannot convert activity into their units, show the
   activity AND write the missing conversion as an open question for the meeting.
5. **Missing data is written as "no data", never modelled.** Metrics that live in a system you
   cannot access (their CRM, finance tool) get the marker, not a guess.
6. **The user's language, plain words.** In Ukrainian avoid anglicisms: прогноз (not форкаст),
   припущення (not драйвери), завантаження команди (not utilization), кваліфіковані ліди.

---

## Inputs: pull before writing

| Input | Source | If missing |
| :-- | :-- | :-- |
| Quarter targets | client's plan, board deck, revenue plan | mark "no plan", build the baseline |
| Actuals by funnel stage | outreach platform, CRM, delivery tracker | "no data" per stage |
| Account health | `client-health-check` output | run it first if installed; otherwise ask the account owner for a 5-line health read and label it self-reported |
| Expansion candidates | `upsell-mapper` output | run it first if installed (the QBR is where expansions land); otherwise list the client's unused services with a reason from this quarter's facts |
| Delivery events of the quarter | PM notes, tickets, releases | ask the delivery lead, 5 questions max |
| Last QBR's commitments | previous QBR page | if none, this is QBR #1; say so |
| Weekly outreach numbers (BOARD mode, outbound channels) | `weekly-outreach-report` pages, if that skill is installed and used | pull from the outreach platforms directly |

`client-health-check` and `upsell-mapper` live in pack `account-management-skills`;
`weekly-outreach-report` lives in pack `outbound-engine-skills`.

---

## Structure: QBR mode

1. Account passport: client, service line, client since, current value, who from their side is in the room.
2. Main point: 3 or 4 sentences. What the quarter delivered, where it slipped, the one step
   for next quarter. Written LAST, read first.
3. Plan and actual: table with a "% of plan" column and a RAG status. Money at the top,
   activities at the bottom.
4. What we did: 3 to 5 events with their effect: event, then what it changed in their numbers.
   A task list does not belong here.
5. Account health: score from the health check and what changed since last quarter.
6. What did not work: mandatory. A review without it reads as a sales pitch and costs trust
   at the next one. One cause, one conclusion, no self-flagellation.
7. Next quarter: 3 to 5 items, each with an owner and a date. Plus what is needed FROM the client.
8. Expansion proposals: 2 or 3 from the cross-sell map, each with a reason from this
   quarter's facts. Framed as an entry step ("at the next status call we'll show how this would
   look for you"), never a pitch. The CTA is never "let's book a call"; the meeting is already happening.
9. Questions for the client: 3 direct ones: what works, what annoys you, what would you stop.

## Structure: BOARD mode

1. Quarter passport: period, active channels, who executed.
2. Main point: one page the board reads if it reads nothing else.
3. Funnel plan and actual: from first touch to money, with ranges (RAG thresholds agreed in advance).
4. By channel: scale, hold or stop. Every verdict states the remaining list size or budget:
   list burnout is the main reason conversion drops, and a blended number hides it.
5. Bottlenecks: presale, salesperson, delivery ceiling (hours × rate). Three at most.
6. Forecast for next quarter, built two ways: top-down (target ÷ deal size ÷ win rate) and
   bottom-up (capacity × conversion rates). The gap between them is the agenda. If installed,
   `revenue-forecast-writer` (pack `gtm-strategy-skills`) builds this section.
7. Levers to close the gap: 3 to 5, each with an expected effect and its cost.
8. Decisions we ask the board for: 1 to 3, each with a deadline. A board pack with no
   decision request is a report.

---

## Process

1. Ask which mode, which account or company, which quarter. Confirm where the plan lives.
2. Pull the inputs. Run `client-health-check` and `upsell-mapper` if their outputs are stale or missing.
3. Fill plan and actual first; the table dictates the story. Do not write the narrative before the table.
4. Draft the sections. Write "Main point" last.
5. If `anticopywriting-ai` (pack `gtm-skills`) is installed, run the prose through it.
6. Save the review where the client's results live: a Notion page under the client's page if
   the Notion connector is available, otherwise a markdown file `<client>-qbr-<YYYY-Qn>.md`.
   Build a deck only when the audience is a board or a room: hand the finished narrative to
   `slide-deck-builder` (pack `sales-engine-skills`, if installed). Never draft in slides first.
7. If `meeting-prep` (pack `sales-engine-skills`) is installed, attach its pre-call block for
   whoever runs the meeting.

## After the meeting: the part that gets skipped

- Summary sent within 24 hours (you draft it; the account owner sends it).
- Commitments go into the CRM and tracker with owner and date.
- Expansion candidates that got a green light go to `proposal-generator` (pack
  `sales-engine-skills`, if installed). Results worth a public story go to `case-study-writer`
  (pack `account-management-skills`, if installed), with the client's permission.
- The next QBR date is booked on this call.

## Cadence

Top accounts quarterly. Everyone else twice a year, or after any delivery phase ends.
A calendar with every top account's QBR date for the next 12 months is part of the definition of done.

## Credits

Method by Victor Shulga (victorshulga.com).
