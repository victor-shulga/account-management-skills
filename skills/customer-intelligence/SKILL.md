---
name: customer-intelligence
description: >
  Find out why clients actually hire a B2B service company, using evidence the company already
  owns: won-deal call notes, client interviews, case studies, named testimonials, Clutch or
  GoodFirms reviews, LinkedIn recommendations. Produces hire reasons ranked by how many clients
  name them, the events that started each search, what clients tried before, quotable proof
  numbers, a bank of the clients' own phrases, honest weak spots and the alternatives they weighed.
  Use when asked "why do clients pick us", "what do our clients say about us", "analyze our
  customers", "find customer pain points", "client language for messaging", "our positioning from
  reviews", or before writing ICP, personas, site copy or outbound sequences.
  Vendor-side research across your own client base. For ONE company you want to sell to, use
  `account-dossier`.
---

# Customer intelligence: why clients hire you

A service company usually explains its wins with its own sales deck. The clients explain them differently, and their version is the one that sells to the next client. This skill collects what clients said, counts it, and turns it into material for ICP work, site copy and outbound.

Treat yourself as the analyst who has to defend every line in front of the founder: each claim in the report points to a source and a count.

**Wrong skill?** If the request names a single company the user wants to win, switch to `account-dossier`. That job needs registry data, decision-makers and a lead score. This one reads many existing clients of one vendor.

---

## 1. Collect the evidence

Ask the user what they have. Service firms rarely have a G2-style footprint, so expect a mix. Rank sources by how close they sit to the client's own mouth:

| Rank | Source | Why it ranks here |
|---|---|---|
| 1 | Recordings or notes from won deals, client interviews (3 to 5 interviews are enough to start) | The client talks before anyone edits the words |
| 2 | Reviews on Clutch, GoodFirms or an industry directory, LinkedIn recommendations from clients | Written by the client, lightly moderated |
| 3 | Case studies and testimonials with a named person and company | Client words, but chosen and polished by the vendor |
| 4 | Lost-deal notes, RFPs and briefs the client sent | Shows what they asked for before they knew you |
| 5 | The vendor's website, deck, proposals | Claims only. Use them to see what the vendor believes, then check against ranks 1 to 4 |

If ranks 1 to 3 are empty, say it plainly and ship a **partial** report: every pain tagged `vendor claim, not confirmed by a client`, and no phrase bank. A phrase bank built from the vendor's own copy feeds the same marketing language back into outbound.

Open an **evidence log** before reading anything, one row per source:

| ID | Type | Client (segment, size, country) | Date | Verbatim? |
|---|---|---|---|---|
| E1 | call notes | mid-size logistics company, DE | 2026-05 | yes |

Every quote and number in the report cites its ID (`E4`). A quote without an ID does not go in.

---

## 2. Read each client story the same way

For every source, fill the same eight fields. Leave a field empty when the source is silent; do not guess.

1. **Before.** What was going wrong in their own words ("drawings came back with clashes every week", "we turned down two projects for lack of people").
2. **The event.** What happened that made them start looking now: a lost tender, a key engineer leaving, a new contract with a deadline, a board asking about margin.
3. **Who pushed.** The role that started the search and the role that signed.
4. **Tried first.** In-house hire, freelancers, another agency, doing nothing. Why it stopped working.
5. **Why you.** The reason they gave for picking this vendor over the others on the shortlist.
6. **After.** What changed, with a number if one exists (hours, cost, turnaround, win rate, headcount avoided).
7. **Doubts.** What almost stopped the deal or what they still complain about.
8. **Phrases.** Exact words worth reusing, copied as written.

Then tag the pain behind each story on four levels. Service-company examples:

- **Task:** "coordination was done by hand in spreadsheets"
- **Business:** "we were losing about one bid in three on delivery time"
- **Personal:** "I was the one checking drawings at 11 pm"
- **Standing:** "the client told our CEO we were the weak link on the project"

The deeper the level a pain reaches, the harder it pulls in outbound. Frequency still decides the ranking: a pain named by 7 of 10 clients beats a vivid one named by a single client. Two sources minimum before a pain gets a rank of its own; a single mention goes to the "seen once" list.

---

## 3. Write the report

```
# Why clients hire [Company]
Evidence: [N sources: x call notes, y reviews, z case studies] · Period: [dates] · Prepared: [date]

## The short answer
[2 to 3 sentences: which clients, which problem pushed them, why they picked this vendor,
what changed for them. Every clause backed by the sections below.]

## Hire reasons, ranked
| # | Reason (client's words) | Named by | Pain level | Strongest quote | IDs |
|---|---|---|---|---|---|
| 1 | | 7 of 10 | business | "..." | E2, E5, E7 |
Seen once (not ranked): [list with IDs]

## Events that started the search
[Each event with a count. These become trigger signals for outbound and the radar.]

## What they tried before
| Tried | Why it stopped working | Quote | IDs |
|---|---|---|---|

## Proof you can quote
| Result | Range across clients | How many clients | IDs |
|---|---|---|---|
[Ranges only from client-side sources. Vendor-only numbers go in a separate row
marked "vendor claim".]

## Who gets the most out of you
[Segment profile: size, industry, country, role of the buyer, the event that brought them.
Share of the evidence that fits it.]

## Phrase bank (verbatim only)
- Problem, as they say it: "..." (E3)
- Result, as they say it: "..."
- Comparison with the alternative: "..."
- Doubt before signing: "..."

## Where clients say you are weak
[Honest list with counts. Mark each as deal-breaker or minor, and whether it is fixed.]

## Alternatives in the deal
[Competitors, in-house, freelancers, "do nothing". Why the client chose this vendor over each,
in the client's words.]

## What waiting costs the buyer
[What clients said they were losing before they acted: money, projects, people, reputation.
Use only what the evidence supports.]

## Hand-off
- Outbound: lead with pains #1 and #2, using these phrases: ...
- Site and case studies: proof rows to feature: ...
- When a prospect names a competitor: the client-voiced reason to switch: ...

## Gaps
[What could not be confirmed and which source would confirm it, e.g. "no lost-deal notes:
ask sales for the last 5 lost proposals".]
```

---

## Rules

- Quote exactly. The phrase bank holds copied words only; your own summaries live in the analysis columns.
- Every row shows its count and its source IDs. "Most clients" without a number is not allowed.
- Vendor claims stay labelled until a client source backs them.
- Weak spots are part of the report even when the user did not ask. A sales team that knows them in advance answers the objection on the call.
- No invented quotes, numbers or client names. If the evidence is thin, the report is short.
- Client names stay inside the user's workspace. Anything that leaves it (site copy, a public post) needs the client's permission or an anonymised segment description.

---

## Where the report goes next

- ICP and personas: run this first, so the ICP rests on why clients bought.
- Outbound copy: the phrase bank and the search-starting events feed cold email and LinkedIn sequences.
- `case-study-writer`: the stories with the strongest numbers become the next case studies.
- Value proposition and offer work: hire reasons ranked 1 to 3 are the starting list.

---

## Check before delivering

- [ ] Evidence log filled, every quote and number carries an ID
- [ ] Each ranked pain has at least two sources and a count
- [ ] Phrase bank is verbatim, nothing from the vendor's own copy
- [ ] Weak spots and alternatives are included
- [ ] Vendor-only claims are labelled
- [ ] A rep could write a first message to a lookalike prospect from this report today

## Credits

Idea adapted from a public outbound-skills collection; rewritten.
Written by Victor Shulga (victorshulga.com).
