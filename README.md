# Strike — Options Strategy Advisor

An AI-powered options analysis tool built on the framework from *Options Trading 101*. Enter a ticker and it researches the underlying, writes an investment thesis, commits to a directional view, and picks the single options strategy that fits — with a payoff diagram and an honest risk/reward check.

**Live demo:** enable GitHub Pages (Settings → Pages → Deploy from branch → `main` / root), then open `https://nefnofap.github.io/options-strategy-advisor/`.

## What it does

The analysis pipeline mirrors the book chapter-for-chapter:

1. **Investment thesis** — Operational, Financial, and Valuation questions ("Developing an Investment Thesis").
2. **Directional view** — Bullish / Bearish / Neutral / Volatile, with a conviction level and horizon.
3. **Matched strategy** — one concrete structure (legs, strikes, expiry, estimated premiums) chosen for the view + IV environment + your risk tolerance, drawn from the full strategy menu (single legs, verticals, straddles/strangles, spreads, butterflies, condors, covered calls, collars, etc.).
4. **Risk / reward check** — the exact "Select an Appropriate Options Strategy" questions, answered: profit if right, if partly right, loss if wrong, and whether you're getting paid enough.

Live data (price, fundamentals, earnings date, IV environment) comes from web search; the reasoning runs through Claude.

## Running it

It's a single `index.html` with no build step.

- **Inside Claude's artifact preview:** works as-is — the Anthropic API call is handled for you, leave the API-key field blank.
- **Self-hosted (GitHub Pages, or open the file locally):** click *self-hosting? add API key* and paste an Anthropic API key. The key stays in your browser and is sent directly to Anthropic; it is never stored or committed.

## Tech

React + Babel (standalone, via CDN), hand-rolled CSS (Hanken Grotesk + JetBrains Mono), SVG payoff diagrams computed client-side from the strategy legs. Model: `claude-sonnet-4-6` with the `web_search` tool.

## Disclaimer

Educational tool, not financial advice. Strikes, premiums, and payoff figures are **illustrative estimates**, not a live options chain — verify everything against your broker before risking capital. Options carry substantial risk of loss. Do your own research.
