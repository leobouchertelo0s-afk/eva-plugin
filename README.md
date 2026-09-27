# eva-plugin

EVA is the AI copilot I use for customer support in iGaming. It started as a Custom GPT with four modes, and colleagues started using it too.

That setup had obvious limits: one big prompt, no history of changes, no way to test that a change didn't break something, and nothing a team could install properly. This repo is my attempt to fix that with Claude: each mode is now a Skill, every change goes through a pull request, and the whole thing installs as a plugin.

All data here is fictional. Nothing from my employer.

## What's in it

Four Skills, one per EVA mode, in `.claude/skills/`:

- `live-chat-reply`: what to answer a player in a live chat
- `optimize-message`: polish a draft without changing the facts
- `ticket-to-inform`: turn an internal answer from another team into an email to the player
- `igaming-expert`: explain concepts like KYC, wagering or self-exclusion (with a glossary)

Each description also says when *not* to use the Skill. With four modes that all deal with player messages, that was the only way to stop them triggering on each other's requests.

An MCP server (the official filesystem server, read-only) gives Claude access to `resources/`, meant for a fictional base of procedures and tickets.

The `.claude-plugin/` folder packages all of it as a plugin.

## Install

Inside Claude Code:

```
/plugin marketplace add leobouchertelo0s-afk/eva-plugin
/plugin install eva@eva-plugin
```

Or clone the repo and open it in Claude Code: the Skills and the MCP server load as project settings. Node.js is needed for the MCP server.

## Tests

Each Skill has a file in `tests/triggers/` with prompts that should trigger it and prompts that shouldn't. I run them by hand, one fresh session per prompt, after any change to a description. Last run on 22/09: everything passes (5/5, 5/5, 5/5, 7/7).

It's manual for now. Automating it is next on the list.

## What's next

- Fill the fictional tickets base (the folder is almost empty)
- Replace the filesystem server with a small MCP server of my own, with real tools like `get_ticket`
- Automate the trigger tests
