---
name: ai-search
description: "Get a website found, read and recommended by AI search: ChatGPT, Claude, Perplexity, Gemini, Google AI Overviews and AI Mode. Use when the user asks about GEO, AEO, AI SEO or LLMO, showing up in ChatGPT or AI answers, why AI doesn't recommend them or recommends a competitor, or AI saying wrong things about their business. Fecto checks what stops AI search reading the site and fixes it at a fixed price, charged only for what Fecto's published checks prove on the live site. Every change is a pull request the owner reviews. Needs the Fecto MCP server."
---

# AI search: readable first, then mentioned

Two different things decide whether AI search recommends a business:
1. **Can it read the site?** Search and assistant bots must be let in (robots.txt and the CDN), the pages must be indexable, and the main text must be in the HTML without JavaScript. Fixable in the repo. Fecto checks it with published rules and charges only for what passes.
2. **Does it trust and pick the business?** Mostly other sites: "best X" lists, review platforms, directories, YouTube, press. Not in the repo. The owner does this work.

## Start
This skill runs with the Fecto MCP server. Once it is connected and the owner has signed in, call `get_skill("ai-search")` and follow the steps it returns: they are the current ones, and this copy carries only the outline.

Not connected yet: in Claude Code, `claude plugin marketplace add makloai/plugins && claude plugin install fecto@makloai`, then `/mcp` to sign in; in Codex, `codex plugin marketplace add makloai/plugins && codex plugin add fecto@makloai`, then `codex mcp login fecto`. Or open fecto.ai, check the site, and choose your agent.

## Never
- Hidden text, prompt injection, "Summarize with AI" links that plant instructions, or content shown only to bots (cloaking).
- Doorway pages for search variations, self-ranked "best X" lists, invented facts, reviews or mentions, or date bumps without a real change.
- Charge talk for llms.txt, FAQ schema or Markdown copies: Fecto never prices them because no engine is shown to use them.

See references/levers.md for what the evidence says works.
