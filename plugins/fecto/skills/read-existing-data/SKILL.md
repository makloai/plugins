---
name: read-existing-data
description: "Read a website's existing traffic, search, enquiry, booking or sales data on the owner's computer and use it to advise on their growth goal before saving a card. Use during Fecto onboarding, when choosing a goal or when the owner asks what their existing numbers imply. Reuses connected tools, accessible reports and exports; does not install tracking or require a new analytics integration. Can work without the Fecto MCP server; raw data stays local."
---

# Read the numbers the owner already has

Do this BEFORE recommending a goal, discussing a proposal and giving the card link. A new tag cannot retrieve historical traffic. Existing Analytics, Search Console, product analytics, booking/order systems and exports may already hold the evidence. Use the owner's agent to read it, explain what it means for their desired result, then return to fix-site's proposal conversation. Keep an answer or goal they already gave.

## Start
This skill runs with the Fecto MCP server. Once it is connected and the owner has signed in, call `get_skill("read-existing-data")` and follow the steps it returns: they are the current ones, and this copy carries only the outline.

Not connected yet: in Claude Code, `claude plugin marketplace add makloai/plugins && claude plugin install fecto@makloai`, then `/mcp` to sign in; in Codex, `codex plugin marketplace add makloai/plugins && codex plugin add fecto@makloai`, then `codex mcp login fecto`. Or open fecto.ai, check the site, and choose your agent.
