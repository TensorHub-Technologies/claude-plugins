# THriveX Live for Claude

Ask Claude about your app's users and improve THriveX Live without opening the console.

| Skill | Run | Does |
|---|---|---|
| Weekly review | `/thrivex-live:weekly-review [app] [days]` | One page: what Live solved, where users got stuck, what to fix first |
| Help writer | `/thrivex-live:help-writer [days]` | Drafts help articles for knowledge gaps and adds the ones you approve; reviews proposed FAQs |
| Setup | `/thrivex-live:setup [app]` | Languages, clicks and deleting, allowed sites, help content, a readiness check |
| IT rollout | `/thrivex-live:it-rollout [windows\|mac\|google]` | Installs the Chrome extension for everyone on managed Chrome and Edge |

Claude also uses the skills on its own when you ask in plain words ("where did users get stuck this week?").

## Before you start

An owner turns Claude on for the company in the THriveX Live console: **Settings › Claude**. Everyone signs in
with their own console account; analysts and the Starter plan can read, owners and admins can also make changes.

## Install in Claude Code

```
/plugin marketplace add TensorHub-Technologies/claude-plugins
/plugin install thrivex-live@tensorhub
```

Then run `/mcp`, choose `plugin:thrivex-live:thrivex-live` and sign in. On claude.ai and in Cowork, add the
connector `https://api.live.thrivex.dev/mcp` under Settings › Connectors.

## What Claude sees

Only what the console shows you: summaries, outcomes and transcripts with personal data masked. Never keys,
audio or screen pictures. Every tool call is recorded in the company's audit log.

Support: https://thub.tech
