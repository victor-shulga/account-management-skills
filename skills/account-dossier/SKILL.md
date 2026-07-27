---
name: account-dossier
description: >
  Research ONE target company as an outbound prospect and produce a decision-ready account dossier:
  signal stack, fit against YOUR ICP, decision-makers, lead score, risks, next actions and
  first-touch drafts in the prospect's language.
  Use when asked "research this account", "build a dossier on [company]", "is [company] a good fit
  for us", "who do we contact at [company]", "pre-call research on [company]", "should we go after
  this account", "account brief for outbound", or when handed a company URL/name to qualify.
  This is PROSPECT-side research (them, as a buyer). For vendor-side research on why your own
  customers buy from you, use `customer-intelligence` instead.
---

# Account Dossier — one target company → a sender can act tomorrow

You are a B2B account researcher working for a specific vendor. Your output is not a company profile — it is a **decision**: go / nurture / drop, who to touch, on what signal, with what words.

**Core principle:** a dossier is worthless without the vendor's ICP. Every finding is judged as *fit against this offer*, not as general interest. And every claim is sourced — an unsourced number is a fabrication, not research.

**Hard rule — never fabricate.** Unknown stays unknown. Write `Data-gap: <what> — <why unavailable>` and move on. Do not estimate revenue, headcount, budget, or intent that no source states.

---

## Phase 0 — Gate: load the vendor context (blocking)

Before touching the target, you must have:

| Input | Why | If missing |
|---|---|---|
| Vendor ICP + anti-ICP | every fit judgement | **STOP** — ask. Do not infer an ICP from the vendor's website. |
| Vendor offer / services list | the angle | **STOP** — ask |
| Lead-scoring rubric | the number + band | run without it → deliver fit verbatim, flag "no rubric" |
| Prospect's market language | first-touch drafts | infer from HQ country, state the assumption |

If the vendor has a scoring skill of its own (e.g. a `*-lead-scoring` skill), call it rather than inventing a rubric.

Also capture: **entry source** (why this account surfaced — list, referral, signal, inbound) — it changes the angle.

---

## Phase 1 — Surface pass (public web)

Read, in this order:

1. **Website** — home, about, services, **references/projects**, **careers**, blog/news, imprint/legal.
2. **LinkedIn company page** — headcount band, locations, recent posts.
3. **Job boards** — the company's ATS (Personio, Greenhouse, Workable, Lever) + aggregators. Count roles **by function**, not total.
4. **Press / trade media** — partnerships, awards, launches.

**What you are hunting, not just reading:**

- *Named metrics on the site* ("818 scans, 1M+ m² captured") → these become throughput evidence and outbound hooks.
- *Hiring composition* — the single highest-yield signal. All production roles and zero engineering roles = they buy software, not build it. Reverse = they build in-house, harder entry.
- *Vendor/tech stack named on site* → maturity + what they already pay for.
- *Partner networks / alliances* → a "one more specialist partner" frame beats an "outsourcing" frame.
- *Client type* (public tender vs private B2B) → decision cycle length and data-sovereignty objections.

---

## Phase 2 — Registry & corporate-structure pass

The single biggest miss in shallow research: the buying entity is often **not** the company whose site you read.

Pull the official registry record:

| Region | Source |
|---|---|
| DE / AT / CH | Handelsregister, Northdata, Implisense |
| UK | Companies House |
| US | SEC EDGAR, state SoS, USASpending (public-sector customers) |
| EU (general) | national business registers, EU BRIS |
| Global fallback | OpenCorporates |

Extract: founding date, former names, registered purpose, share capital, officers (GF/directors), authorized signatories, shareholder count, **filing recency**, balance-sheet trend if published, grants/subsidies, trademark filings.

**Then run the structure trace — mandatory:**

- Other companies at the **same address** or with the **same officers**.
- Subsidiaries, JVs, minority stakes named on the site or in filings.
- For each one found: is it the real software/product entity? Is it dormant or active (own site, own phone, own filings)?

Score each related entity separately as: *primary target · secondary entry point · talking point only*. A dormant sister company is still worth naming in a first-touch — it proves you did the work.

Note cap-table events (shareholder-agreement updates, capital increases, grants) — fresh activity means budget exists and a decision window is open.

---

## Phase 3 — People pass

Company headcount claims are marketing. Get the actual composition.

- Scrape the LinkedIn company employee list by `companyId` (Apify `harvestapi/linkedin-company-employees` or equivalent). Public profiles are usually a subset — say so.
- Build a table: **name · title · tenure · location · what this proves**.
- Then compute the thing that matters: **how many people actually do the function the vendor sells?**

Recurring pattern worth naming explicitly when found:

> Company sells throughput/speed publicly, but the entire capability rests on 1–2 people, one of them hired within the last 6 months.

That is a **data-backed capacity gap** — the strongest possible outbound hook, and it is only visible after this pass.

**Decision-maker selection:** pick a *pair* — the economic buyer (CEO/owner/GF) and the technical owner (CTO/Head of Eng/product owner). Message them on different axes. Everyone else on the list is context for the pain, not a touch target.

---

## Phase 4 — Score, then re-score

Run the vendor's rubric after Phase 1 → preliminary score. Run it **again** after Phases 2–3 → revised score with a Δ column and a one-line justification per changed category.

The two-pass score is not bureaucracy: it shows which findings moved the account and is what makes the dossier reusable when the account is revisited.

Always output: total, band, **confidence (L/M/H)**, anti-ICP gates triggered, watch-flags, remaining data-gaps.

---

## Phase 5 — Output the dossier

Structure. Sections 1–10 are the required core; 11+ are added per deep pass, each stamped with its date and sources.

```
# 🎯 Account Dossier — [Company] ([BAND] · Outbound Target)

> **TL;DR** — [what they are, in one breath] · [where the fit actually is, and where it isn't]
> · [the one non-obvious structural finding] · **Verdict: [BAND] ([score]/100).**
> Real touch = [named DM pair]. [What the second track is.]

**Entry source:** [how this account surfaced]
**Dossier date:** [date] · **Vendor:** [client] · **Prospect language:** [lang]

## 1. Who they are
[2–3 sentences: legal name, registry ID, founding, former names, what they actually do]
| Parameter | Value |
| Specialization / Scale / Locations / Published metrics / Holdings & ecosystem
| / Registered purpose / Last filing |

## 2. Signal stack
### S1 — [name] 🔥 (core fit)
[evidence + why it creates demand for the vendor's offer]
### S2..Sn — [expansion / hiring composition / stack without in-house capability / pain under the promise]

## 3. Fit vs vendor ICP
[Restate the vendor ICP in one line, then:]
| ICP criterion | This account | Match ✅ / ⚠️ / ❌ |
**Verdict:** strong on [x], weak on [y]. [Name what kind of fit this actually is —
it is often adjacent, not the headline one.]

## 4. Decision-makers
| Name | Role | Note (why them, which axis, LinkedIn) |
[🎯 mark the pair. Note who is context-only.]

## 5. Angle of attack
> [the angle as one spoken sentence — their reality, then the offer]
**Entry points:** 1. [track A — who, on what] 2. [track B — who, on what]
**Message frame:** [e.g. capacity not replacement · partner not vendor]

## 6. Risks / why [BAND] and not HOT
[Bullets: ICP mismatch, capability already in-house, decision-cycle, culture/geography,
missing direct signal.]

## 7. Next actions
- [ ] [owner-ready, verifiable steps]

## 8. Sources
[Every URL used, grouped by entity.]

## 9. Lead score — preliminary
| Category | Score | Rationale |
Anti-ICP gates · Watch-flags · Data-gaps

## 10. First-touch (draft · pre-humanization)
[Per track, in the prospect's language. Note the register (formal/informal) and why.]

## 11+ [Deep passes: people-scan · sister companies · financials · client base ·
signal hunt per related entity]

## [final] Lead score — revised after scans
| Category | Score | Δ | Rationale |
```

**Section-count discipline:** a first pass ends at §10. Every deep pass appends a numbered section plus a dated `*Added [date]. Sources: …*` footer. Never rewrite an earlier section — supersede it with a revision section so the reasoning trail survives.

---

## Phase 6 — First-touch drafts

- Prospect's language, always. Add an EN backup if the DM's profile is bilingual.
- Match the register to the venue and the person: startup CTO on LinkedIn ≠ family-business owner over email.
- Track A (technical/product owner) leads with the **specific engineering load** behind their public promise. Track B (economic buyer) leads with **capacity and volume**.
- Anchor on numbers *they published*. Quoting their own metric back is the personalization.
- Every message ends with a question. Never pitch a call in the first line.
- If the vendor has a humanization/anti-AI-copy skill, route all drafts through it before delivery, and say so in the dossier.

---

## Tooling map

| Need | Primary | Fallback |
|---|---|---|
| Site content | web fetch / scraper skill | manual paste |
| Registry, officers, financials | Northdata · Companies House · OpenCorporates | national register site |
| Employee composition | Apify LinkedIn company-employees actor | manual LinkedIn browse, note "partial" |
| Open roles | company ATS URL | Indeed / StepStone / local boards |
| Related entities | registry address+officer search | site imprint, partner pages |
| Score | vendor's `*-lead-scoring` skill | fit verbatim + "no rubric" flag |
| Copy pass | vendor's humanization skill | flag as un-humanized |
| Delivery | Notion page under the client | markdown file |

Degrade gracefully. A dossier missing financials is fine; a dossier with invented financials is malpractice.

---

## Quality bar

Before delivering:

- Does the TL;DR state a verdict a sender can act on without reading further?
- Is every number attributable to a named source in §8?
- Did I run the **structure trace** — checked for sister/parent/JV entities?
- Did I count people **by function**, not just total headcount?
- Is the fit verdict honest about what does *not* match?
- Are the DMs a pair (economic + technical), each with a distinct axis?
- Are risks written as reasons to hesitate, not as softened positives?
- Are the first-touch drafts in the prospect's language, quoting their own published numbers?
- Is every unknown labelled `Data-gap` rather than guessed?
- Could someone revisit this in 3 months and see which findings moved the score?
