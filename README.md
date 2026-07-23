# account-management-engine

Account management skills for B2B service companies: client health scoring, upsell mapping, case study production.

Part of the GTM-system methodology by [Victor Shulga](https://victorshulga.com) (Fractional CRO).

## Install (Claude Code)

```
/plugin marketplace add victor-shulga/account-management-skills
/plugin install account-management-engine@account-management-skills
```

Restart your Claude Code session after install — skills load at session start.

## Skills included

- **`case-study-writer`** — a finished project → a publishable case study in the 12-section Case Study Kit structure (result-first snapshot → 3-type Challenge → 1:1 Solution → before→after Results → testimonial → CTA → SEO), plus the SME interview questionnaire, a designer visual brief and a pre-launch checklist. Outputs 3 formats: website page, one-pager PDF outline, LinkedIn handoff.
- **`client-health-check`** — scores every active account green / yellow / red on 6 health criteria and outputs a health table + an action plan for the reds.
- **`upsell-mapper`** — builds a client × services cross-sell matrix, finds the gaps, and prioritizes the realistic expansion moves.
- **`deep-company-analyser`** — deep account/company research from website, case studies and reviews → pains, buying triggers, customer language and competitive positioning. Powers account dossiers and pre-engagement research.

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
