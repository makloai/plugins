---
name: connect-events
description: "Optional. Use when the owner asks to connect Fecto backend events, so bookings, orders or sign-ups are counted from their server instead of the browser tag. Inspect the owner's backend, add signed reporting after successful business actions, test without counting events, and verify live receipts. Needs Fecto MCP and access to the site's backend repo."
---

# Connect Fecto measurement in the owner's project



## Start
This skill runs with the Fecto MCP server. Once it is connected and the owner has signed in, call `get_skill("connect-events")` and follow the steps it returns: they are the current ones, and this copy carries only the outline.

Not connected yet: in Claude Code, `claude plugin marketplace add makloai/plugins && claude plugin install fecto@makloai`, then `/mcp` to sign in; in Codex, `codex plugin marketplace add makloai/plugins && codex plugin add fecto@makloai`, then `codex mcp login fecto`. Or open fecto.ai, check the site, and choose your agent.
