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

- `case-study-writer`
- `client-health-check`
- `upsell-mapper`

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
