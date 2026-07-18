# What's Hot Today

A demand-arbitrage scanner for TikTok Shop sellers. It finds products with proven market demand (Amazon bestseller movement, trend data) that still have a supply and content gap on TikTok Shop, then scores each one 0–100 on a green-to-red profitability scale.

**Live demo:** open `index.html` in a browser, paste an Anthropic API key, and hit Scan.

## The idea

Product research tools usually answer "what's selling?" This one answers a sharper question: **where has demand been proven on one platform while distribution is still underpriced on another?**

Amazon's bestseller and Movers & Shakers data is validated demand — someone else already paid to prove people buy the product. TikTok Shop is a distribution channel where content saturation lags behind that demand. The arbitrage lives in the window between the two. A product everyone on TikTok is already selling scores *low* here even if demand is enormous, because the gap — the actual asset — is closed.

## How scoring works

Every candidate is scored on five weighted components:

| Component | Weight | What it measures |
|---|---|---|
| Demand signal | 30 | Evidence of real, current sales velocity across sources |
| TikTok gap | 25 | How open the opportunity still is — saturation kills this score |
| Demonstrability | 15 | Whether the product sells itself in a 15-second video |
| Margin structure | 20 | Estimated markup from bulk sourcing (3x+ scores full marks) |
| Logistics | 10 | Small, light, unbreakable, evergreen, unregulated |

Composite bands: **Green ≥ 75** (act on it), **Amber 50–74** (needs an angle), **Red < 50** (skip). The deliberate design choice: a viral product with massive demand and a closed gap lands in amber or red. The scanner is built to flag late entries, not celebrate them.

## How it works technically

Single-file vanilla HTML/CSS/JS — no framework, no build step, no backend.

- The search query and active filters are compiled into a structured research prompt
- The prompt is sent to the Anthropic API (Claude Sonnet) with the web search tool enabled, so every scan runs on live data rather than a stale database
- The model is constrained to return strict JSON, which is parsed and rendered as ranked cards with a thermal score bar per product
- Your API key lives in a password field in memory only — never stored, never sent anywhere except Anthropic's API

## Honest limitations

- No scraped Amazon sales data. Signals come from live web research, so scores are directional rankings of bets, not precision forecasts.
- One scan returns 4 candidates by design — this is a triage instrument, not a catalog.
- Trend windows on TikTok are short; a green score is an argument for testing 10 units this week, not for a warehouse order.

## Roadmap

- Scan history with score tracking over time (watch a gap close in real time)
- Sourcing-cost lookup pass against wholesale listings
- Category presets tuned to TikTok Shop's highest-GMV verticals

---

Built by G — Connecticut. Part of a portfolio exploring scoring systems and funnel logic applied to real markets
**All future updates and design tweaks will be included below**

(07-18-2026)-I have changed the font so its less robotic as well as added a dynamic selection for products.Ive included an expanded view that holds the three primary buttons that would be in use, currently placeheld by amazon, tiktok,and aliexpress but I am planning to make these plug and play for the websites the user desires.
