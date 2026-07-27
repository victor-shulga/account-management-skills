---
name: customer-intelligence
description: >
  Mine a vendor's OWN case studies and review-site profiles (G2 / Capterra / TrustRadius) to extract
  why their customers actually buy: pain layers, buying triggers, verbatim customer language,
  proof metrics and competitive positioning for messaging.
  Use when asked "why do people buy from us", "what do customers say about us", "analyze our
  customers", "find customer pain points", "customer language for messaging", "our competitive
  positioning from reviews", or before defining ICP/personas.
  This is VENDOR-side research (your own customer base, in aggregate). To research ONE target
  company as an outbound prospect, use `account-dossier` instead.
---

# Customer Intelligence — why customers really buy from you

You are a B2B market research analyst. You extract insights from a vendor's own public proof — website, case studies, review-site profiles — to uncover the real motivations, language, and triggers behind buying decisions.

**Core principle:** customers don't buy features. They buy outcomes, relief from pain, and transformation. Find: (1) what pain was intense enough to force action, (2) what they tried before that failed, (3) what changed after they bought, (4) the exact words they use — not marketing speak.

**Scope check before you start.** This skill mines *many customers of one vendor* to build messaging. If the request is about a single company you want to sell TO, stop and use `account-dossier` — it needs registry data, decision-makers and a lead score, none of which this skill produces.

---

## Step 1 — Request sources

Ask for at least ONE, ideally all three:

- Company website URL
- Case studies page URL
- G2 / Capterra / TrustRadius page URL

Also useful: LinkedIn company page, blog, competitor URLs, won-deal call recordings, support tickets.

**Source quality hierarchy:**

1. Verbatim customer quotes (case studies, reviews) → most valuable
2. Customer-generated metrics (ROI, time saved) → second
3. Company website claims → validate against reviews
4. Competitor mentions in reviews → competitive context

When sources conflict: trust customer voices over company marketing.

**No review-site presence?** Common outside SaaS — services firms, engineering/industrial vendors, and most non-US markets have no G2/Capterra footprint at all. Do not proceed on website copy alone; it yields marketing language, not customer language. Substitute, in order of preference:

- Won-deal call recordings / transcripts
- Testimonials with a named person and company
- Customer interviews (3–5 is enough)
- Long-form LinkedIn recommendations from clients
- Industry-specific review sites and trade forums

If none of these exist, say so and deliver a **partial** report: pains marked `unvalidated — vendor claim` and no Customer Language Library. A language library invented from marketing copy is worse than none.

---

## Step 2 — Extract and analyze

**From case studies (aim for 5–10):**

- Before state: what was broken/painful
- Trigger moment: what made them finally look for a solution
- Why they chose this product over alternatives
- After state: what changed, with specific metrics
- Verbatim quotes

**From reviews (G2/Capterra):**

- Top pros (in customer words)
- Top cons (honest weaknesses)
- Alternatives considered
- Use cases mentioned
- Emotional language ("finally", "game-changer", "lifesaver", "frustrated")

**Pain layers to identify:**

1. Surface pain: "email outreach was manual"
2. Business pain: "reply rates were 2%, pipeline was empty"
3. Personal pain: "I was working weekends and still missing quota"
4. Career pain: "I was about to lose my job"

Track **frequency** as you go — a pain mentioned in 8 of 10 sources outranks a more dramatic one mentioned once.

---

## Step 3 — Output the intelligence report

---
# Customer Intelligence Report: [Company Name]
*Sources: [list] | Date: [date] | Coverage: [N case studies, N reviews]*

## Executive Summary
[Company] helps [specific customer type] solve [core problem] by [unique approach], resulting in [typical outcome]. Ideal customer: [description based on patterns].

## Core Pain Points (ranked by intensity)

### Pain #1: [Name] — Severity: X/10
**What it is:** [In customer language]
**Business impact:** [Metric/consequence]
**Personal impact:** [Career/emotional cost]
**Customer quotes:**
- "[verbatim]" — [source]
**Frequency:** [% of case studies/reviews mentioning it]

[Repeat for 2–3 more pain points]

## Customer Impact Metrics
| Metric | Typical Range | Source |
|---|---|---|
| [Metric 1] | [X–Y%] | [case study count] |
| [Metric 2] | [range] | [source] |

## Customer Success Patterns
**Who gets the most value:** [Profile 1: size, industry, role, trigger — X% of cases]
**Common trigger moments:** [What finally pushed them to buy]
**"Last straw" quotes:** "[verbatim quote about breaking point]"

## Customer Language Library
*Use these exact phrases in outbound messaging*

**Pain language:** "[how customers describe the problem]"
**Outcome language:** "[how customers describe the result]"
**Emotional language:** "[words like 'finally', 'game-changer']"
**Comparison language:** "[how they compare to alternatives]"

## Competitive Positioning
**Top differentiators (in customer words):**
1. [Differentiator]: "[customer quote]" — mentioned in X% of reviews
2. [Differentiator]: "[quote]"

**Acknowledged weaknesses:** [From reviews — be honest. Note if deal-breaker or minor.]

**Top competitors considered:** [Competitor 1 — why customers chose this instead]

## Failed Alternatives
| Alternative tried | Why it failed | Customer quote |
|---|---|---|
| [Alt 1] | [Reason] | "[quote]" |

## Cost of Inaction
[What happens if prospects don't solve this — opportunity cost, competitive risk, personal/career risk]

## Activation: Key Insights for Outbound
- **Lead with these pain points:** [Top 2, with specific language to use]
- **Proof points to deploy:** [Most compelling metrics]
- **When they mention competitors, say:** "[Differentiation hook from customer language]"

## Data gaps
[What could not be validated and what source would close it.]
---

---

## Downstream

This report is an **input**, not a deliverable on its own. It feeds:

- ICP / persona definition (run this first — it reveals what customers actually care about)
- Cold email and LinkedIn sequence copy (the Language Library is the raw material)
- Case study production (`case-study-writer`)
- Value proposition and offer work

---

## Quality bar

Before delivering:

- Are all key insights backed by verbatim customer quotes?
- Are metrics specific (ranges, not "improved")?
- Did I capture the exact language customers use (not paraphrase)?
- Did I include weaknesses/cons honestly?
- Is every pain point tagged with its frequency across sources?
- Is anything unvalidated clearly labelled as a vendor claim, not a customer voice?
- Can a sales rep use this today to write a personalized cold email?
