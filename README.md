# Tranche

**A fixed-rate lending and yield tokenization protocol.**

## The problem

Yield-bearing positions today are all-or-nothing: you hold the asset and get whatever variable yield the market gives you, with no way to lock in a fixed return or separately trade your view on where yield is headed. Institutional users in particular need predictable, fixed returns for planning purposes — but on-chain yield rarely offers that without giving up upside entirely.

## What Tranche does

Tranche splits a yield-bearing asset into two separately tradeable tokens: a Principal Token, redeemable for the original deposit at a set maturity date (giving a fixed return), and a Yield Token, which captures the variable yield and can be bought or sold separately by anyone wanting to speculate on future interest rates. A purpose-built automated market maker allows price discovery specifically for these future-yield trades.

Core features:
- **Principal/Yield splitting** — any supported yield-bearing asset can be split into a fixed-return component and a variable-yield component
- **Fixed-rate access** — holding the Principal Token to maturity behaves like a zero-coupon bond, locking in a known return
- **Yield speculation** — the Yield Token lets traders take a leveraged view on whether future yield will rise or fall, without needing to hold the full underlying position
- **Dedicated yield AMM** — a market maker model built specifically for pricing future yield, rather than repurposing a general-purpose spot AMM
- **Composable Principal Tokens** — fixed-return tokens can be used as collateral elsewhere in DeFi, since their value profile is predictable

## Why this model works

Yield tokenization has proven itself as a major DeFi primitive elsewhere, with the leading implementation peaking at somewhere between $8 and $13 billion in total value locked — proof that splitting yield into separately tradeable fixed and variable components meets real institutional and retail demand simultaneously. Institutions in particular have used this kind of structure to hedge billions of dollars of yield exposure, something that simply is not possible when yield-bearing assets can only be held whole.

## What this unlocks

- A structured-finance layer on top of existing lending and yield-bearing assets, rather than requiring a whole new asset class
- Fixed-rate access for institutional users who need predictable returns for planning purposes
- A new instrument for traders who want to speculate on yield direction specifically, independent of the underlying assets price
- Composable, low-risk collateral (the Principal Token) that other DeFi protocols can accept with more confidence than the raw variable-yield asset

## Status

🚧 Early development. See open issues for current priorities across `/frontend`, `/backend`, and `/contracts`.

## Repo structure

```
frontend/    Next.js/TypeScript app — split/redeem UI, PT/YT trading, maturity dashboard
backend/     Rust service — yield accrual tracking, maturity scheduling, indexer
contracts/   Soroban smart contracts — splitting vault, PT/YT tokens, yield AMM
```

## Contributing

Issues are open and welcome contributions across all three layers. See individual issue labels for scope and difficulty.
