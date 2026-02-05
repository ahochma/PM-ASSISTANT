---
stepsCompleted: [1, 2, 3, 4, 5, 6]
inputDocuments:
  - domain-order-templates-cfd-trading-product-research-2026-02-03.md
  - ../One click trade/prd.md
  - ../One click trade/product-brief-one click trade.md
date: 2026-02-03
author: Amit.hochma
workflowType: create-product-brief
productFocus: Order Templates (Phase 3 of Fast Trading / One-Click Trade)
---

# Product Brief: Order Templates for CFD Trading

**Product:** Order Templates (Order Presets)  
**Context:** Phase 3 of Fast Trading / One-Click Trade mobile product (Plus500)  
**Research Basis:** [domain-order-templates-cfd-trading-product-research-2026-02-03.md](./domain-order-templates-cfd-trading-product-research-2026-02-03.md)

---

## Executive Summary

**Product Vision:**  
Enable CFD traders to save and reuse common order configurations—contract size, stop-loss, take-profit, order type—so they can apply them with one action instead of re-entering parameters every time. Order Templates reduce **configuration friction**; One-Click Trading reduces **execution friction**. Together they support fast, consistent trading for day traders and scalpers.

**Core Problem:**  
Active CFD traders who use one-click trading still re-enter the same order parameters (size, SL, TP) on every trade. This repetition adds taps and cognitive load, slows execution, and creates inconsistency. Traders with recurring strategies (e.g., 1-contract scalps, 5-contract swings with 20-tick SL) want to pre-set and reuse these configurations.

**Proposed Solution:**  
Order Templates (Order Presets) that let users save named configurations and apply them via a dropdown in the order ticket. A default template pre-fills the Fast Trading bottom sheet and watchlist order entry. Users can still edit values before executing. Templates complement one-click: they pre-fill; one-click executes.

**Expected Impact:**  
Higher order frequency, faster order entry, and better consistency for active traders. Success measured by template creation rate, apply rate, and correlation with order frequency.

---

## Core Vision

### Problem Statement

Day traders, scalpers, and active CFD traders who use one-click trading still spend time re-entering the same order parameters—contract size, stop-loss, take-profit, order type—on every trade. There is no way to save and reuse these configurations across instruments or sessions.

### Problem Impact

When traders must re-enter parameters each time:
- **More taps** – Slows order entry and creates friction even with one-click
- **Inconsistency** – Manual entry increases the risk of typos or wrong values
- **Cognitive load** – Repeated decisions reduce focus on market analysis
- **Missed opportunities** – Slower setup can mean missed entries

### Why Existing Solutions Fall Short

- **CMC Markets** – Default SL/TP in Order Settings only; no named templates for different strategies
- **IG (MT5)** – Chart templates only; no order parameter presets
- **Retail CFD platforms** – Typically offer single global defaults, not multiple named presets
- **Pro platforms (IBKR, TradingView, Quantower)** – Full template support, but often desktop-first; mobile implementations are lighter

### Proposed Solution

Order Templates that allow users to:
1. **Save** order configurations (size, SL, TP, order type) with a custom name
2. **Apply** a template via dropdown in the order ticket (bottom sheet or watchlist row)
3. **Set a default** template that pre-fills new order entry
4. **Edit** any value before executing (templates populate; they do not bypass review)

Templates integrate with the Fast Trading bottom sheet and watchlist expandable row. Default template is stored with one-click preference and applied when opening order entry from Chart, Info tab, or Watchlist.

### Key Differentiators

1. **Synergy with One-Click** – Templates + one-click = fast configuration and fast execution
2. **Mobile-First** – Designed for mobile: touch targets, short preset names, default template for quick flow
3. **CFD-Aligned** – Parameters match CFD needs (contracts, SL/TP in ticks or %)
4. **Regulatory-Safe** – Templates pre-fill; user sees and can change values before execution

---

## Target Users

### Primary Users

#### Persona: Alex – The Mobile Day Trader

**Background & Context:**  
Alex is the same persona as for One-Click Trading: an experienced day trader who trades CFDs on mobile, ~20 trades/day, small quick positions. Alex has already adopted one-click trading and now wants to reduce the time spent setting up each order.

**Motivations & Goals:**
- Reuse the same size + SL + TP across instruments
- Switch between strategies (e.g., scalp vs swing) quickly
- Reduce taps and cognitive load
- Keep risk parameters consistent

**Current Problem Experience:**
- Re-enters 1 contract + 20-tick SL + 40-tick TP on every scalp
- Sometimes forgets to set SL or uses wrong size
- Wastes time when switching between strategies

**Success Vision:**
- Select "1-contract scalp" preset → fields fill → tap Buy/Sell
- Switch to "5-contract swing" preset in one tap when opportunity changes
- Never re-enter the same configuration twice

**Key Characteristics:**
- One-click trading enabled
- Uses 1–3 recurring configurations
- Values speed and consistency
- Mobile-primary

### Secondary Users

- **Swing traders** – Fewer trades but larger sizes; benefit from consistent SL/TP presets
- **Multi-instrument traders** – Same template across instruments; may later want per-instrument templates

### User Journey

#### Journey: Alex Enables and Uses Order Templates

**Discovery:**
- Sees "Order Templates" or "Trading Presets" in Settings > Trading
- Or sees "Save as preset" when order ticket is filled (first time or from help)

**Setup:**
1. Alex opens order ticket, enters 1 contract, 20-tick SL, 40-tick TP
2. Taps "Save as preset" → names it "1-contract scalp" → saves
3. Optionally sets it as default in Settings

**Core Usage:**
1. Alex opens order entry from Chart, Info tab, or Watchlist
2. Default template ("1-contract scalp") pre-fills size, SL, TP
3. Alex confirms or tweaks → taps Buy/Sell (one-click executes)
4. For a different strategy, Alex selects "5-contract swing" from preset dropdown → fields update → executes

**Success Moment:**
- Alex notices they placed 5 trades in the time it used to take for 3
- No typos or forgotten SL/TP
- Feels the platform matches their workflow

---

## Success Metrics

### User Success Metrics

**Primary User Outcomes:**
- Users create at least one template
- Users apply templates regularly when placing orders
- Users report faster, more consistent order entry

**User Success Indicators:**
- **Template creation rate** – % of eligible users who create ≥1 template
- **Template apply rate** – % of orders that use an applied template (among users with templates)
- **Default template usage** – % of order entry sessions that use the default template

### Business Objectives

**Primary Business Goal:**  
Increase order frequency and consistency by reducing configuration friction, building on the one-click execution improvement.

**Measurement Approach:**
- Compare orders per user: template adopters vs non-adopters (control)
- Track template creation and apply events
- Correlate template usage with order frequency

**Target Metrics (Post-Baseline):**
- **Template creation rate:** 20–30% of one-click users create ≥1 template
- **Template apply rate:** 50%+ of orders from template users use a template
- **Orders per user:** 5–10% increase for template adopters vs control (on top of one-click effect)

### Key Performance Indicators

| KPI | Definition | Target |
|-----|------------|--------|
| Template creation rate | % of eligible users who create ≥1 template | 20–30% |
| Template apply rate | % of orders using a template (among template users) | 50%+ |
| Default template usage | % of order sessions with default template applied | 40%+ |
| Orders per user (template adopters) | vs control group | +5–10% |

**MVP Success Validation:**
- Usage and funnel metrics tracked
- No increase in errors or support tickets
- Targets set after baseline from one-click MVP

---

## MVP Scope

### Core Features

**1. Create Order Templates**
- Save template from filled order ticket: "Save as preset" → name → save
- Parameters: contract size, stop-loss, take-profit, order type (Market/Limit)
- Optional: manage templates in Settings (create, edit, delete, set default)

**2. Apply Order Templates**
- Preset dropdown in order ticket (bottom sheet for Chart/Info tab; watchlist expanded row)
- Selecting preset populates size, SL, TP, order type
- User can edit any value before execution
- Default template pre-fills when opening order entry

**3. Default Template**
- Set one template as default in Settings
- Default applied when opening order entry from Chart, Info tab, Watchlist
- Stored with one-click preference

**4. Integration with Fast Trading**
- Works with Fast Trading bottom sheet (Chart, Info tab)
- Works with watchlist expandable row order entry
- Templates only pre-fill; order execution uses existing flow
- Compatible with one-click (pre-fill → confirm size → Buy/Sell executes)

**5. Template Limits**
- MVP: 1–3 templates per user (global, apply to all instruments)
- Short, descriptive names (e.g., "1-contract scalp", "5-contract swing")

### Out of Scope for MVP

- **Per-instrument templates** – Defer to v2 if usage justifies
- **Conditional order templates** – Trigger-based logic (e.g., if price > X)
- **Advanced parameters** – TIF, brackets, multi-order groupings
- **Template sharing** – User-to-user or platform-provided templates

### MVP Success Criteria

- Template creation and apply metrics tracked
- No increase in errors or support tickets
- Integration with Fast Trading and one-click validated
- User feedback supports faster, more consistent order entry

### Future Vision

**Post-MVP (v2):**
- Per-instrument templates (last-used or saved preset per symbol)
- More templates per user (e.g., 5–10)
- TIF, brackets, advanced order options in templates
- "Smart defaults" based on user behavior

**Long-Term:**
- Conditional order templates
- Template suggestions from usage patterns
- Cross-device sync and template management

---

## Relationship to One-Click Trading

| Aspect | One-Click Trading (Phase 1) | Order Templates (Phase 3) |
|--------|-----------------------------|---------------------------|
| **Friction Reduced** | Confirmation step | Configuration (size, SL, TP) |
| **User Action** | Single tap to execute | Single tap to apply preset |
| **Integration** | Bottom sheet, watchlist | Same surfaces; pre-fills fields |
| **Complement** | Templates pre-fill → one-click executes | |

Order Templates are explicitly listed in the One-Click Trade PRD Phase 3 ("Order templates and presets," "Smart defaults based on user behavior"). They extend the Fast Trading value proposition for active traders.

---

## Design Implications (from Research)

- **Preset selector:** Dropdown or chip list in order ticket header or above size selector; 44×44pt (iOS) / 48×48dp (Android) touch targets
- **Save preset:** "Save as preset" when order ticket is filled; modal for name
- **Settings:** "Order Templates" or "Trading Presets" in Settings > Trading
- **Accessibility:** Screen-reader friendly preset names; clear indication of active preset

---

## Technical Considerations (from Research)

- **Data model:** `id`, `userId`, `name`, `parameters` (size, SL, TP, orderType), `isDefault`, `createdAt`, `updatedAt`
- **Persistence:** Per user; backend validation at apply time
- **Integration:** Fast Trading bottom sheet accepts preset; pre-populates fields; same order submission API
- **Analytics:** Template create, apply, default change events

---

## Next Steps

1. **Product:** Refine Phase 3 PRD section for Order Templates; define success metrics and baseline approach
2. **Design:** Wireframes for preset selector in bottom sheet and watchlist row; preset management in Settings
3. **Engineering:** Define template data model and API; plan integration with Fast Trading component

---

*Product brief synthesized from domain research: [domain-order-templates-cfd-trading-product-research-2026-02-03.md](./domain-order-templates-cfd-trading-product-research-2026-02-03.md)*
