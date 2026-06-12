# Strike — Options Strategy Advisor

An AI-powered options analysis tool built on the framework from *Options Trading 101*. Enter a ticker and it researches the underlying, writes an investment thesis, commits to a directional view, and picks the single options strategy that fits — with a payoff diagram and an honest risk/reward check.

**Live demo:** enable GitHub Pages (Settings → Pages → Deploy from branch → `main` / root), then open `https://nefnofap.github.io/options-strategy-advisor/`.

## What it does

The analysis pipeline mirrors the book chapter-for-chapter:

1. **Investment thesis** — Operational, Financial, and Valuation questions.
2. **Directional view** — Bullish / Bearish / Neutral / Volatile, with conviction and horizon.
3. **Matched strategy** — one concrete structure (legs, strikes, expiry, estimated premiums) chosen for the view + IV environment + your risk tolerance, with an SVG payoff diagram.
4. **Risk / reward check** — the "Select an Appropriate Options Strategy" questions, answered: profit if right, if partly right, loss if wrong, and whether you're getting paid enough.

## Two engines — pick free or premium

Strike runs on either of two backends, chosen automatically:

| | Engine | Live data | Cost | Where it works |
|---|---|---|---|---|
| **Default** | Claude (`claude-sonnet-4-6`) + web search | built-in web search | needs Claude access | inside Claude's artifact preview |
| **Free** | Google Gemini 2.5 Flash + Finnhub | Finnhub quote/fundamentals | **$0, no credit card** | anywhere, incl. GitHub Pages |

Leave the key fields blank and it uses Claude. Paste a **free Gemini key** and it switches to the free engine; add a **free Finnhub key** so the price and fundamentals are live rather than estimated.

- Gemini free key: https://aistudio.google.com/apikey (no card — Flash/Flash-Lite free tier)
- Finnhub free key: https://finnhub.io/register (no card — US-listed quotes + fundamentals)

Keys live only in your browser and are sent directly to Google / Finnhub. They are never stored or committed.

## Running it

Single `index.html`, no build step.

- **Inside Claude's artifact preview:** works as-is, leave keys blank.
- **GitHub Pages / local file:** open *API keys*, paste the free Gemini (and ideally Finnhub) key, done.

## Tech

React + Babel (standalone, via CDN), hand-rolled CSS (Hanken Grotesk + JetBrains Mono), SVG payoff diagrams computed client-side from the strategy legs.

## Disclaimer

Educational tool, not financial advice. Strikes, premiums, payoff figures, and the IV read are **illustrative estimates**, not a live options chain — verify against your broker before risking capital. Options carry substantial risk of loss. Do your own research.
