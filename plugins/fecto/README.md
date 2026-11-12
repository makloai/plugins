# Fecto for Claude Code and Codex

Fix your website for a result you pay for only when Fecto's published checks prove it on the live site: AI search readability (ChatGPT, Claude, Perplexity, Google AI), answers to your buyers' questions, speed, working forms and more conversions. Every change is a pull request you review.

## Install

Claude Code:

```
claude plugin marketplace add makloai/plugins
claude plugin install fecto@makloai
```

Inside a session, `/plugin marketplace add makloai/plugins` and then `/plugin install fecto@makloai` do the same. Then run `/mcp`, choose fecto and sign in.

Codex:

```
codex plugin marketplace add makloai/plugins
codex plugin add fecto@makloai
codex mcp login fecto --scopes mcp,offline_access
```

The last command opens your browser to sign in to Fecto.

Or open fecto.ai, check your site and pick your agent: it opens with Fecto's instructions typed in.

## Skills

- `fecto:fix-site`: check a site, agree one result with the owner, and work toward it one pull request at a time.
- `fecto:read-existing-data`: read existing accessible traffic, search, enquiry, booking or sales reports locally before recommending a goal. Uses connected tools, existing reports or exports; no new tracking integration required.
- `fecto:connect-events`: optional. Count bookings, orders or sign-ups from your backend instead of the tag: the agent adds signed events in your repo, tests without counting, and verifies real receipts. You configure the backend key privately.
- `fecto:ai-search`: get a site read and recommended by ChatGPT, Claude, Perplexity, Gemini and Google's AI answers. Reads Search Console on your computer.
- `fecto:campaign-page`: a page in your own site for one promotion, ad, email or post, with a tracked link per place you post it, and how many visits and enquiries it brought.
- `fecto:get-mentioned`: get listed on the review sites, directories and "best of" pages AI search cites for your buyers' questions. Your agent asks AI search itself; Fecto checks each listing and charges only for ones it finds live.
- `fecto:move-to-code`: move a Wix, Squarespace or Webflow site into a repo you control, compared page by page before the domain moves. Fecto hosts nothing.
- `fecto:dashboard`: a local dashboard of the numbers that matter for your site, from your own Search Console, GA4, PostHog, Plausible or Stripe. Doesn't need a Fecto account.

Ask in your own words ("check my site with Fecto", "why doesn't ChatGPT recommend us?"); the agent picks the skill.

## How it works

1. **Free scan and your score.** Check the site on fecto.ai, then open your local coding agent. Or start in the agent; it reuses a saved scan when available.
2. **A conversation in your agent.** The agent first reads already accessible historical reports with read-existing-data and explains their sources, dates and gaps alongside the scan. Discuss the business result you want, what the evidence suggests, how Fecto can help, plan options, pricing, budget and any concerns. The agent can calculate a smaller budget, pay-as-it-grows pricing, allowed discounts and a suitable duration before you save a card. No new tag, Analytics or backend setup first. If data is unavailable, the agent labels its advice provisional; it does not invent a baseline or block the conversation.
3. **Your proposal, then your card.** When you are ready, the agent saves the chosen goal and terms and gives you a secure link. The webpage shows that proposal and lets you save your card with $0 due today; it does not replace the conversation. Saving a card accepts no paid plan and starts no deadline.
4. **Technical setup afterwards.** Return to the agent. It keeps the saved commercial terms, adds the Fecto tag (backend events are optional), then produces the formal quote with real qualifying counts for you to accept. No repeat goal questionnaire or silent return to standard pricing.
5. **The work.** Fecto hands the agent one step at a time. Changes arrive as pull requests you review and merge. No repo? The agent explains supported site-builder steps.
6. **The check.** Fecto verifies the agreed result. Only verified results on accepted plans are billable, within the saved pricing and the $100/site/month total cap.
7. **Round after round.** When a round ends, the next starts by itself on the same terms: from the new level after a met round, with approaches the site hasn't had after a missed one ($0). The agent tells you when a step is new. A short email each month says what was done and where the numbers stand. Stop any time from the plan page.

The skills here are a fallback: each session the agent loads the current version from Fecto with `get_skill`, so there's nothing to update by hand.

Your agent never accepts prices, merges or changes settings outside the repo (DNS, CDN, hosting); you do. Search Console and analytics are read on your computer, and only the numbers you agree to share reach Fecto.

Privacy: https://fecto.ai/privacy

## Existing data before the card (0.7.4)

read-existing-data is available as an installed skill and through get_skill. fix-site, ai-search, the web-to-agent prompt and MCP onboarding guidance now read existing reports before recommending a goal. Data stays in the local agent conversation; Fecto pricing tools do not analyze or automatically receive it. New tracking and backend setup remain after the card. Update the plugin and reconnect MCP to load the new instructions.

## Agent-led onboarding (0.7.3)

The webpage scans and opens your agent. Goals, proposals, budget, price and questions stay in the agent before the card. get_onboarding/goal_options calculate adjustable proposals without measurement prerequisites; prepare_checkout saves the chosen terms and returns the card link. Those terms are restored for setup and the formal quote. This replaces 0.7.2’s web-based goal selection. Update the plugin and reconnect MCP to discover prepare_checkout and the new inputs.

## Measurement setup (0.7.0)

The Fecto tag counts your results by default, and nothing more is needed. If your site has a backend and you want results counted from it, ask: "Use Fecto to connect backend events for my site." The agent inspects your backend, adds the integration and tests, and opens a PR. Installing the plugin alone does not modify your site. Dry-run tests never count toward billing; a live receipt is checked after deployment. Existing installations need the plugin update to discover the new skill; fix-site also loads current instructions with get_skill.

## Developing

The skills Fecto serves (everything except `dashboard`) are public outlines: what each is for, how to connect and what it never does. The full steps come from the Fecto MCP server's `get_skill` once the agent is signed in. Regenerate the outlines from the live server:

```
for n in fix-site read-existing-data connect-events move-to-code ai-search campaign-page get-mentioned; do curl -sf https://fecto.ai/skills/$n.md > plugins/fecto/skills/$n/SKILL.md; done
```

`dashboard` runs on the owner's computer without Fecto, so it ships in full here.

Bump `version` in both `.claude-plugin/plugin.json` and the repository's `.claude-plugin/marketplace.json`, and check with:

```
claude plugin validate --strict plugins/fecto
claude plugin validate --strict .
```

The MCP server URL in `.mcp.json` must be the URL Fecto names as its own (`https://fecto.ai`): sign-in tokens are only good for that URL.
