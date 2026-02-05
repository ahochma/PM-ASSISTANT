---
stepsCompleted: [1, 2, 3, 4, 5]
inputDocuments:
  - Fast Trading/One click trade/product-brief-one click trade.md
  - Fast Trading/One click trade/market-fast-trading-one-click-trade-mobile-research-2026-02-01.md
date: '2026-02-01'
author: Amit.hochma
---

# Product Brief: BMAD-METHOD

## Executive Summary

**Product Vision:** Enable one-click market order execution directly from the full-screen chart on mobile. This allows day traders, scalpers, and active traders to enter the market with a single action, without losing the chart context, which is critical for their trading decisions.

**Core Problem:** Active CFD traders who rely on chart analysis face significant friction when placing orders. The current flow often requires leaving the chart, leading to context loss and missed opportunities.

**Proposed Solution:** A one-click trading system from the chart, where users can execute market orders via a bottom sheet that preserves chart visibility. Users set trade size and choose buy/sell, and the order executes immediately.

**Expected Impact:** More submitted orders per user by reducing friction and enabling faster, in-context market entry.

---

## Core Vision

### Problem Statement

Day traders, scalpers, and active CFD traders need to enter the market quickly. They mostly use market orders and want fast execution, but the current flow requires several steps instead of one, and often forces them to leave the chart.

### Problem Impact

When traders cannot enter quickly from the chart: they miss opportunities, trading efficiency drops, order frequency falls, and frustration rises—with risk to platform engagement.

### Why Existing Solutions Fall Short

One-click exists elsewhere but with inconsistent safety/UX, mobile not always speed-first, setup complexity, and misalignment with how active traders actually trade (e.g. contract size + buy/sell as the only approval from the chart).

### Proposed Solution

One-click system with: (1) instant execution after trade size + buy/sell, (2) mobile-first, minimal taps from the chart, (3) smart defaults (e.g. last size), (4) safety via design and explicit opt-in, (5) clear post-order feedback (price, size, P&L on close, auto-dismiss).

### Key Differentiators

1. **Speed-First Philosophy** – Fastest execution while keeping safety.
2. **Mobile-Native Experience** – Built for mobile trading workflows, starting with the chart.
3. **User-Centric Defaults** – Learns from behaviour to reduce setup.
4. **Metrics-Driven** – Measure usage, quality, and funnel to learn and iterate; set targets after baseline.

---

## Entry Points for One-Click Trading

For Phase 1, one-click market orders are available exclusively from the chart.

### Chart Entry

**Buy or Sell directly from the chart.** This is the primary entry point for active traders. Users can trigger the one-click flow (size + buy/sell) from the chart context without leaving the chart view, preserving their analysis and connection to market movements.

### Settings Opt-In + Feedback

- **Opt-in:** One-click trading is **enabled via a settings toggle** with **terms acceptance** before the feature is available.
- **Feedback:** After execution, show a **short confirmation** (e.g. execution price, size, and for closes realised P&L) with auto-dismiss so the user knows the order went through.

---

## Target Users

### Primary Users

#### Persona: Alex – The Mobile Day Trader

**Background & Context:** Experienced day trader who primarily trades CFDs on mobile. Executes approximately 20 trades per day, focusing on small, quick positions to capitalize on short-term market movements. Trades throughout the day, often on the go; mobile device is the primary trading tool. Relies heavily on chart analysis.

**Motivations & Goals:** Speed (enter and exit quickly), efficiency (minimize friction), frequency (many trades per day), mobile-first experience that doesn't break chart context.

**Current Problem Experience:** Today’s flow requires leaving the chart to place a market order; friction slows execution, reduces frequency, causes frustration when speed matters.

**Success Vision:** Fastest way into the market from the chart, minimal friction, higher trade frequency, never miss an opportunity due to slow flow or context switching.

**Key Characteristics:** ~20 trades/day, primarily mobile, small frequent positions, experienced, quick entries/exits, market orders, chart-focused.

**Emotional Drivers:** Frustration when opportunities are missed; satisfaction when entering quickly; confidence when the platform supports fast trading from the chart.

### Secondary Users

Not a focus for MVP; optional later (e.g. support, oversight).

### User Journey – Alex’s Trading Session

**Discovery:** Already on platform; discovers one-click from chart via notification, settings, or first-time prompt when placing a market order from the chart.

**Onboarding:** “Enable one-click trading for faster market orders?” → short explanation → enable or learn more → optional brief tutorial.

**Core Usage:** (1) Identify opportunity on mobile chart, (2) tap Buy/Sell on the chart, (3) select size in the bottom sheet (quick selector or default), (4) order executes (one-click), (5) brief success message, sheet dismisses, (6) repeat with minimal friction, staying on the chart.

**Success Moment:** Enters in seconds instead of multiple clicks and screen changes; trades more frequently; feels the platform supports their style.

**Long-term Value:** One-click from chart becomes default; more orders per user; reduced frustration; platform essential for day trading workflow.

---

## Success Metrics

Success is measured by **usage**, **quality**, and **funnel**—without fixed business or adoption targets until we have a baseline. We measure to learn and iterate.

### User Success (Outcomes We Care About)

- **Faster execution** – Users who have one-click enabled can place market orders with fewer steps from the chart.
- **Repeat use** – Opted-in users who come back and use one-click again (signal that the flow is useful).
- **No regression** – No increase in errors, accidental orders, or support load attributable to one-click.

### How We Measure This Feature

**1. Usage (among opted-in users)**

- **One-click usage rate** – Of all market orders placed by users who have one-click enabled, what % use the one-click flow from the chart?
  *Measures whether the feature is used when available.*
- **One-click orders per opted-in user** – Count of one-click orders per user per period (e.g. per week).
  *Measures intensity of use; no target, observe and compare over time.*

**2. Funnel (setup and first use)**

- **Opt-in funnel** – How many users see the opt-in (e.g. in settings or prompt), start it, complete terms, and enable one-click?
  *Measures whether the opt-in flow works; drop-off points inform UX changes.*
- **Time to first one-click order** – Among users who opt in, how long until they place their first one-click order?
  *Measures how quickly the feature gets into their workflow.*

**3. Quality & safety**

- **Opt-out rate** – % of users who enable one-click then later disable it.
  *Signal of poor fit or safety concerns.*
- **Errors and support** – Error rate on one-click orders; support tickets or escalations linked to one-click.
  *Guardrails; aim for no increase vs baseline.*

**4. Learning-first, targets later**

- **Adoption** – We observe how many eligible users opt in but do **not** set a “success” adoption target until we have data.
- **Business impact** – We can later correlate one-click usage with orders per user or volume if needed; not defined as success criteria for the feature itself.

### Key Performance Indicators (Summary)

| What we measure | Why |
|-----------------|-----|
| One-click usage rate (among opted-in users) | Is the feature used when available? |
| One-click orders per opted-in user | How much do adopters use it? |
| Opt-in funnel (see → start → complete → enable) | Does setup work? Where do we lose people? |
| Opt-out rate | Do people turn it off? |
| Errors / support linked to one-click | Is it safe and stable? |

*Targets (e.g. “X% usage rate” or “Y% opt-in”) can be set after we have a baseline and a few release cycles.*

---

## MVP Scope

### Core Features

**1. One-Click Market Order Execution from Chart**
- User sets **number of contracts** (manual, presets, or chips), then chooses **Buy or Sell** → order executes with no extra confirmation when one-click is enabled.
- Available from: **Chart** only.

**2. Settings Opt-In + Feedback**
- **Opt-in:** Settings toggle + **terms acceptance** before one-click is available; short explanation (orders execute without a second confirmation).
- **Feedback:** Short confirmation after execution (price, size; for closes: realised P&L), auto-dismiss (e.g. 2–3 seconds).

**3. Order Entry (Bottom Sheet from Chart)**
- A bottom sheet is used for order entry, preserving chart visibility.
- Contains: Buy/Sell side, symbol, live price, contract size, balance/validation.
- **Market orders only** for MVP; behaviour depends on one-click toggle (standard confirm vs instant).

**4. Entry Points**
- **Chart** – Buy/Sell from chart (primary for active traders).

**5. Quality & Rollout**
- Real-time balance/margin validation; clear errors; analytics for usage, funnel, quality; support for gradual rollout.

### Out of Scope for MVP

- All other entry points (Watchlist, Info Tab, Positions, etc.).
- Limit / stop orders; TP/SL inline; quote lock; position awareness in order flow; order templates; web/desktop; alert-triggered orders.
- **In scope for MVP:** Chart entry only.

### MVP Success Criteria

- **Usage:** One-click usage rate and orders per opted-in user (observe; no fixed targets yet).
- **Funnel:** Opt-in funnel (see → start → complete → enable) and time to first one-click order.
- **Quality:** No rise in errors or support; low opt-out rate.
- **Decision:** Proceed beyond MVP when we have baseline data and no quality regressions; set targets after learning.

### Future Vision

- Additional order types (limit, stop); TP/SL inline; quote lock; position awareness; more entry points (e.g. alerts); web/desktop; smarter defaults and templates.