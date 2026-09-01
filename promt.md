# Daily Cross-Asset Macro Screener

Run each weekday morning (UK time). Produce a snapshot of overnight
and premarket moves, tied to the news driving them.

## What to capture

**Government bond yields** — prior close → current level, in bp:
- UK 10y gilt
- US 10y Treasury (and 2y)
- German 10y bund
- Japan 10y JGB
- France 10y OAT

**Equity indexes** — prior close → premarket/futures:
- FTSE 100, S&P 500, Nasdaq 100, Euro Stoxx 50, DAX, CAC 40, Nikkei 225

**Gold** — prior close → current spot, in USD and %

## Method

1. Search for current levels and overnight moves for each asset above.
2. For any move that stands out, search the news to find what drove it.
3. Read `data/` — the previous daily files — before writing. Note where
   today continues, contradicts, or escalates a theme already running.

## Output

Write a new file: `data/YYYY-MM-DD.md`, structured as:

- **Headline** — one line on what defined the session
- **Rates** — table of levels and bp moves, with drivers
- **Equities** — table of levels and % moves, with drivers
- **Gold** — level, move, driver
- **Themes** — what's carrying over from previous days, and what's new
- **Watch** — data releases or events in the next 24h that matter

Use exact figures throughout. No rounding to "about" or "roughly".
