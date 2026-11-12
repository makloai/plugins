---
name: move-to-code
description: "Move a website from Wix, Squarespace or Webflow into a code repo the owner controls, so fixes the builder can't make become possible. Use when the user wants to move off Wix, Squarespace or Webflow, rebuild their site in code, or when a Fecto step is blocked because the builder can't do it. Fecto lists every live page and what must survive, then compares the rebuilt copy page by page before the domain moves; Fecto hosts nothing. Needs the Fecto MCP server."
---

# Move a no-code site into code (only if the owner wants it)

Fecto hosts nothing. You rebuild the site here and deploy it on a host the owner signs up for. Fecto lists what must survive and compares the new copy with the live site before the domain moves.

## Start
This skill runs with the Fecto MCP server. Once it is connected and the owner has signed in, call `get_skill("move-to-code")` and follow the steps it returns: they are the current ones, and this copy carries only the outline.

Not connected yet: in Claude Code, `claude plugin marketplace add makloai/plugins && claude plugin install fecto@makloai`, then `/mcp` to sign in; in Codex, `codex plugin marketplace add makloai/plugins && codex plugin add fecto@makloai`, then `codex mcp login fecto`. Or open fecto.ai, check the site, and choose your agent.

## Never
- Create accounts, enter passwords or move the domain yourself.
- Drop a page, form, booking widget or contact link the inventory lists.
