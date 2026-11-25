# Mojobase for Claude

The Mojobase connector, and skills that teach Claude real jobs in your business, done in
[Mojobase](https://mojobase.ai), where your email, team chat, calendar, tasks, files, Handbook, customers and numbers
live together.

| Skill | Ask Claude | What you get |
| --- | --- | --- |
| `morning-run-through` | "What needs me today?" | Today's meetings, tasks due, who's waiting on a reply and who's late paying, with the replies already drafted |
| `chase-who-owes-you` | "Who owes us money? Chase them." | One polite reminder per late customer, with the payment link, unless someone agreed to wait (Stripe invoices in US dollars, connected in Mojobase) |
| `prepare-for-a-call` | "Prep me for my call with Leo." | A one-page brief from the mail, notes, files, tasks and invoices behind that meeting |
| `week-review` | "How did the week go?" | What got done, what's slipping, the numbers, and next week's three priorities as suggested tasks |
| `business-profile` | "Tell Mojobase about my business." | Your Handbook's business profile filled in from what you tell Claude, for every agent to read first |

## Before you start

Mojobase is invite-only for now: [request a founding spot](https://mojobase.ai/signup).

## The connector

The plugin bundles the Mojobase MCP connector, `https://app.mojobase.ai/mcp` (`.mcp.json`). Connect it once: sign in
with your Mojobase account and pick your company. No key or secret is stored in the plugin. In Claude Code you can use
a Mojobase key instead (Agents → Connected), as the [Claude guide](https://mojobase.ai/agents/claude) shows; the
skills use whichever connection you made.

## Install

**claude.ai and Claude Desktop:** Customize → Plugins → Add → Add marketplace, enter `mojobase/skills`,
then add Mojobase. Connect Mojobase on the plugin's Connectors tab: sign in and pick your company. Your skills appear
under Customize → Skills; type `/` in a chat to pick one, or just ask.

**Claude Code:**

```
/plugin marketplace add mojobase/skills
/plugin install mojobase@mojobase
```

Type `/mcp`, pick the plugin's Mojobase server and sign in (or skip this if you already connected Mojobase with a
key). Then ask, or run one by name: `/mojobase:morning-run-through`.

**Claude Cowork:** a plugin you add in Customize is on your account, so Cowork loads these skills in your next task.

## What it sends and changes

The skills send nothing themselves. They tell Claude which Mojobase tools to use, through the connector,
acting as you with your permissions. Every email they write is a draft you send yourself; they never send or schedule
email, and never delete anything. Tasks and documents follow your own settings in Mojobase: suggestions you accept,
unless you set that kind of change to Auto. Notes on an invoice, and on a meeting when you ask, are saved as they're
written.

## License

MIT
