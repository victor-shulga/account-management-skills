# account-management-engine

Account management skills for B2B service companies: client health scoring, upsell mapping, case study production.

Part of the GTM-system methodology by [Victor Shulga](https://victorshulga.com) (Fractional CRO).

## Install (Claude Code)

Type these in the Claude Code chat (slash commands, not your shell):

```
/plugin marketplace add victor-shulga/account-management-skills
/plugin install account-management-engine@account-management-skills
```

Restart your Claude Code session after install — skills load at session start.

## Update

Run these **in your terminal** (not in the Claude Code chat). The first refreshes the cached marketplace catalog — without it Claude Code will not see the new version; the second updates the plugin itself:

```bash
claude plugin marketplace update account-management-skills
claude plugin update account-management-engine@account-management-skills
```

Then restart Claude Code — skills load at session start, so an update is not live until you do.

Prefer not to use a terminal? Type `/plugin` in the Claude Code chat to open the plugin manager and update from there.

Check what you have installed:

```bash
claude plugin list
```

## Skills included

- **`case-study-writer`** — a finished project → a publishable case study in the 12-section Case Study Kit structure (result-first snapshot → 3-type Challenge → 1:1 Solution → before→after Results → testimonial → CTA → SEO), plus the SME interview questionnaire, a designer visual brief and a pre-launch checklist. Outputs 3 formats: website page, one-pager PDF outline, LinkedIn handoff.
- **`client-health-check`** — scores every active account green / yellow / red on 6 health criteria and outputs a health table + an action plan for the reds.
- **`upsell-mapper`** — builds a client × services cross-sell matrix, finds the gaps, and prioritizes the realistic expansion moves.
- **`account-dossier`** — research ONE target company as an outbound prospect → signal stack, fit against your ICP, decision-maker pair, two-pass lead score, risks, next actions and first-touch drafts in the prospect's language. Ships a built-in 100-point rubric (anti-ICP gates → 9 categories → band → action) that defers to your own approved rubric when you have one. Includes the corporate-structure trace (sister/JV entities are often the real buying entity) and the people-scan that turns "they're hiring" into a data-backed capacity gap.
- **`customer-intelligence`** — mine your OWN case studies and review-site profiles → why customers actually buy: pain layers, triggers, verbatim customer language, proof metrics, competitive positioning. Run before defining ICP/personas.

> **Which one?** `account-dossier` = prospect-side, one company you want to sell TO. `customer-intelligence` = vendor-side, your own customer base in aggregate. They take different inputs and produce different outputs — picking the wrong one is the most common misfire.

## Requirements & integrations

| Integration | Used for | Required? | Auth / setup |
|---|---|---|---|
| Claude Code | running the skills | yes | claude.com/claude-code |
| Notion MCP | writing reports/audits as Notion pages | optional | connect Notion in Claude settings |
| Outreach platform MCP (Instantly / HeyReach / Grinfi / Aimfox) | pulling live campaign & reply data | optional | connect the platform you use |
| CRM MCP | pulling deals/accounts | optional | connect your CRM |

Skills degrade gracefully: without MCP connections they work from pasted data (CSV, sheets, text).

## License

MIT — see [LICENSE](LICENSE).
