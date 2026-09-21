# eva-plugin

EVA is an AI copilot for customer support agents. It started as a Custom GPT used by a support team.
This repo turns it into a Claude plugin: versioned Skills, reviewed through pull requests, and an MCP server that gives EVA access to procedures and tickets.

All data in this repo is fictional.

## Status

Work in progress.

## Planned structure

- `skills/`: one folder per EVA mode
- `mcp-server/`: MCP server exposing a fictional procedures and tickets base
- `tests/`: update, access and audit tests
