---
name: campaign-page
description: "Build a page for one promotion, ad, email or social post in the owner's own site, with a link per place it's posted, and read how many visits and enquiries it brings. Use when the owner is about to run a sale, an event, an ad or a newsletter, asks for a landing page, or wants to know which post or channel brings enquiries. The page is part of their enquiries result, never a separate charge. Needs the Fecto MCP server."
---

# A page for a campaign

Sending people from an ad or a post to the home page loses most of them. A page made for exactly that offer, with one clear way in, turns more of them into enquiries. You build it in the owner's repo; Fecto's tag counts its visits and enquiries.

## Start
This skill runs with the Fecto MCP server. Once it is connected and the owner has signed in, call `get_skill("campaign-page")` and follow the steps it returns: they are the current ones, and this copy carries only the outline.

Not connected yet: in Claude Code, `claude plugin marketplace add makloai/plugins && claude plugin install fecto@makloai`, then `/mcp` to sign in; in Codex, `codex plugin marketplace add makloai/plugins && codex plugin add fecto@makloai`, then `codex mcp login fecto`. Or open fecto.ai, check the site, and choose your agent.

## Never
- Invent an offer, a price, a discount, a deadline, a testimonial or a number of customers.
- Add a countdown or "only 2 left" that isn't true.
- Post, send or pay for the campaign for the owner.
