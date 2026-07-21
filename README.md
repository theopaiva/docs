# Yellow Guide — Mintlify test build

A faithful Mintlify reproduction of https://docs.yellow.pro/ for testing whether
Mintlify renders the GitBook structure the same way.

## What's inside
- `docs.json` — full navigation (2 tabs: Guide + API Reference, all 64 pages, matching Yellow's tree)
- `index.mdx`, `getting-started/what-is-yellow.mdx`, `spot-trading/how-to-place-a-spot-trade.mdx`
  — real content, showing the GitBook→Mintlify block conversions
- Every other page — placeholder with correct title/description frontmatter

## GitBook → Mintlify conversions demonstrated
| GitBook | Mintlify |
|---|---|
| `{% hint style="info" %}` | `<Info>` / `<Note>` / `<Warning>` |
| `<table data-view="cards">` | `<CardGroup>` + `<Card>` |
| `{% tabs %}` / `{% tab %}` | `<Tabs>` / `<Tab>` |
| numbered card list | `<Steps>` / `<Step>` |
| `SUMMARY.md` | `navigation` in `docs.json` |
| `.md` + hint blocks | `.mdx` + components |

## How to test it
1. Install the CLI: `npm i -g mint`
2. From this folder: `mint dev` → opens http://localhost:3000
3. To publish: push this folder to a GitHub repo and connect it in the Mintlify dashboard.

## Migrating for real
Replace each placeholder body with the matching GitBook page. Every source page is
available as Markdown by appending `.md` to its URL (e.g.
https://docs.yellow.pro/fees/vip-tiers.md), which you can paste in and convert.
