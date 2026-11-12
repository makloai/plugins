---
name: get-mentioned
description: "Get a business listed on the third-party pages AI search actually reads: review platforms, directories, \"best X\" lists. Use when the user asks to get listed, get on best-of lists, get more reviews, do PR or directory submissions, or asks why AI recommends a competitor. Fecto maps the pages ChatGPT, Perplexity and Claude cite for the owner's buyer questions, drafts honest pitches the owner sends, and charges per profile or listing only once its check finds it live. Needs the Fecto MCP server."
---

# Get mentioned where AI looks

Being named by AI search depends mostly on other sites. Fecto lists the pages the engines cite for the owner's buyer questions, drafts a pitch for each, and checks the pages later. The owner sends every pitch; you never post, email, create accounts or pay.

## Start
This skill runs with the Fecto MCP server. Once it is connected and the owner has signed in, call `get_skill("get-mentioned")` and follow the steps it returns: they are the current ones, and this copy carries only the outline.

Not connected yet: in Claude Code, `claude plugin marketplace add makloai/plugins && claude plugin install fecto@makloai`, then `/mcp` to sign in; in Codex, `codex plugin marketplace add makloai/plugins && codex plugin add fecto@makloai`, then `codex mcp login fecto`. Or open fecto.ai, check the site, and choose your agent.

## Never
- Buy placements or reviews, or pitch a "best X" list that ranks the owner first.
- Post on Reddit, forums or review sites for the owner, or write reviews.
- Claim a listing Fecto hasn't checked.
