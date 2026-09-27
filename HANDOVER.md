# Handover

Notes for whoever maintains this after me, or for me in three months.

## Changing a Skill

Never on `main`. New branch, change, rerun that Skill's trigger tests (`tests/triggers/`), update the date in the file, pull request, merge.

If you touch a description, rerun the tests of the other Skills too. Descriptions compete with each other: making one broader can steal requests from another.

## Things that already broke

**22/09, MCP server not starting in the desktop app.** The app doesn't inherit the terminal's `PATH`, so it couldn't find `npx`. Fixed with the absolute path (`which npx`). That's why `.mcp.json` has `/opt/homebrew/bin/npx`. The plugin config uses plain `npx` so it works on other machines, which means this can come back in the desktop app. If the server doesn't show up, check this first.

**22/09, a test that looked green but wasn't.** Claude read the file with its `Bash` tool, not through the MCP server. The answer was right, the test was wrong. Always expand the tool call and check the tool name.

**22/09, the server saw more folders than configured.** The client also sends its own "roots" (the open project). Worth knowing before pointing this at anything sensitive.

## Rules

- No real company or player data in this repo, ever.
- No keys or tokens. If one gets pushed by mistake: revoke it first, clean the repo after.
