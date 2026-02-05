---
stepsCompleted: [1, 2, 3, 4, 5]
inputDocuments: 
  - Fast Trading/Bottom sheet/fast-order-component-product-solution.md
  - Fast Trading/Bottom sheet/market-research-order-submission-ux.md
  - Fast Trading/Bottom sheet/epics-and-stories.md
date: 2026-01-27
author: Amit.hochma
---

# Product Brief: BMAD-METHOD

## Executive Summary

**Product Vision:**
Enable one-click market order execution for CFD traders **directly from the chart on mobile**. This allows day traders, scalpers, and active traders to enter the market instantly without losing the chart context that is critical to their decisions.

**Core Problem:**
Active CFD traders who rely on market orders and chart analysis face friction in the current order placement flow. Placing an order requires leaving the chart, breaking their analytical flow and causing missed opportunities.

**Proposed Solution:**
Implement a one-click trading system from the chart that allows users to execute market orders immediately via a bottom sheet that preserves chart visibility, eliminating confirmation steps and reducing time-to-execution.

**Expected Impact:**
Increase the number of submitted orders per user by reducing friction and enabling faster, in-context market entry for active traders.

---

## Core Vision

### Problem Statement

Day traders, scalpers, and active CFD traders need to enter the market quickly to capitalize on opportunities identified on the chart. These users primarily place market orders and want fast execution, but the current flow requires multiple steps and forces them away from their primary analysis tool—the chart.

### Problem Impact

When traders cannot enter the market quickly from the chart:
- They miss time-sensitive opportunities
- Context switching reduces trading efficiency
- Friction reduces order frequency
- User frustration increases, potentially reducing platform engagement

### Why Existing Solutions Fall Short

While some platforms offer one-click trading, they often fail to preserve the chart context, which is a major pain point for technical traders on mobile.

### Proposed Solution

A one-click trading system focused on the chart experience:
- **Instant Execution from Chart**: Market orders execute immediately after trade size selection from a chart overlay.
- **Mobile-First Design**: Optimized for mobile with minimal taps, preserving chart visibility.
- **Smart Defaults**: Remembers user preferences to reduce configuration.
- **Safety Through Design**: Built-in safeguards without adding confirmation steps.
- **Clear Feedback**: Immediate visual confirmation of order execution.

### Key Differentiators

1. **Chart-Centric Philosophy**: Optimized for the fastest possible execution while maintaining chart context.
2. **Mobile-Native Experience**: Designed specifically for mobile trading workflows from the chart.
3. **User-Centric Defaults**: Learns from user behavior to reduce setup time.
4. **Metrics-Driven**: Focused on increasing orders per user through reduced friction.

---

## Target Users

### Primary Users

#### Persona: Alex - The Mobile Day Trader

**Background & Context:**
Alex is an experienced day trader who primarily trades CFDs on mobile, relying heavily on chart analysis. They execute approximately 20 trades per day, focusing on small, quick positions to capitalize on short-term market movements.

**Motivations & Goals:**
- **Speed**: Enter and exit positions quickly to capture opportunities.
- **Efficiency**: Minimize friction and context switching.
- **Frequency**: Execute many trades per day.
- **Mobile-First**: Needs a seamless mobile experience that keeps them on the chart.

**Current Problem Experience:**
- Today's flow requires leaving the chart to place an order.
- This friction slows execution, causing missed opportunities and frustration.

**Success Vision:**
- The fastest way to get into the market, directly from the chart.
- Trade more frequently due to reduced friction and preserved context.
- Never miss an opportunity due to slow execution or screen changes.

**Key Characteristics:**
- **Trading Frequency**: ~20 trades per day
- **Device Preference**: Primarily mobile
- **Trading Style**: Chart-based, quick entries/exits, market orders.

**Emotional Drivers:**
- Frustration when opportunities are missed due to slow execution or context loss.
- Satisfaction when entering positions quickly while staying on the chart.
- Confidence when the platform supports a fast, chart-centric workflow.

### User Journey

#### Journey: Alex's Trading Session from the Chart

**Discovery:**
- Alex discovers the feature through a prompt when first trying to trade from the chart.

**Onboarding:**
- Alex sees a prompt: "Enable one-click trading from the chart for faster market orders?"
- A quick explanation of the feature is provided.
- If enabled: A brief tutorial shows the simplified chart-based flow.

**Core Usage - Typical Trading Session:**
1. **Market Analysis**: Alex identifies a trading opportunity on the mobile chart.
2. **Order Entry**: Taps the Buy/Sell button on the chart.
3. **Size Selection**: A bottom sheet appears over the chart. Alex selects trade size.
4. **Instant Execution**: Order executes immediately (one-click enabled).
5. **Confirmation**: A brief success message appears, and the sheet dismisses, returning Alex to the full chart.
6. **Repeat**: Alex places multiple orders throughout the day with minimal friction, never leaving the chart.

**Success Moment:**
- Alex realizes they entered a position in seconds, without ever leaving the chart.
- They trade more frequently because it's faster and they don't lose their analysis.

**Long-term Value:**
- One-click trading from the chart becomes Alex's default method.
- Alex trades more frequently (increased orders per user).
- The platform becomes essential for their day trading workflow.

**Pain Points Addressed:**
- ✅ Eliminates friction of leaving the chart.
- ✅ Reduces missed opportunities.
- ✅ Enables faster execution in context.
- ✅ Supports high-frequency, chart-based trading.

---

## Success Metrics

### User Success Metrics

**Primary User Outcomes:**
- **Faster Trading**: Users execute market orders with reduced friction from the chart.
- **Increased Order Frequency**: Users place more orders due to reduced friction.
- **One-Click Adoption**: Users opt-in to one-click trading.

**User Success Indicators:**
- **One-Click Adoption Rate**: Percentage of eligible users who opt-in.
- **Feature Usage Rate**: Percentage of market orders placed via one-click from the chart.
- **Order Frequency Increase**: Increase in orders per user for adopters.

### Business Objectives

**Primary Business Goal:**
Increase the number of submitted orders per user by reducing friction and enabling faster market entry.

---

## MVP Scope

### Core Features

**1. One-Click Market Order Execution (Primary Feature)**
- **Instant Execution**: Market orders execute immediately after contract size selection (when one-click enabled).
- **From Chart Only**: This feature is exclusively available from the chart in the MVP.

**2. Integration with Fast Trading Bottom Sheet Component**
- **Component Relationship**: One-click trading works WITH the existing Fast Trading bottom sheet component, initiated from the chart.
- **Two Modes**: 
  - **Standard Mode**: Bottom sheet with confirmation step.
  - **One-Click Mode**: Bottom sheet with instant execution (no confirmation) when user opts in.

**3. Contract Size Selection (Works with Bottom Sheet)**
- **Manual Input**: Users enter number of contracts directly.
- **Quick Presets**: Common contract sizes as quick-select buttons.
- **Default Size**: Remembers last used contract size per instrument.
- **Real-time Validation**: Balance/margin validation before execution.

**4. Opt-In/Onboarding Flow**
- **Settings Toggle**: Users enable one-click trading via app settings.
- **Terms Acceptance**: Users must accept terms before enabling.

**5. Order Entry Interface (Leverages Fast Trading Bottom Sheet)**
- **Bottom Sheet Component**: Uses existing Fast Trading `QuickOrderSheet` component, launched from the chart and preserving chart visibility.

**6. Real-Time Validation & Error Handling (Bottom Sheet Feature)**
- **Balance Validation**: Real-time margin/balance checks.
- **Inline Errors**: Clear, actionable error messages.

**7. Success Confirmation**
- **Order Confirmation**: Brief success message with order details.
- **Auto-Dismiss**: Bottom sheet dismisses automatically after 2-3 seconds.
- **Return to Context**: User returns to the chart.

**8. Feature Toggle & A/B Testing**
- **A/B Testing Capability**: Support for gradual rollout.
- **Analytics Tracking**: Comprehensive event tracking.

### Relationship Between Features

**Fast Trading Bottom Sheet (Existing/In Development):**
- Reusable order entry component with bottom sheet overlay.
- Standard flow includes confirmation step.
- For this product, it is initiated from the **Chart**.

**One-Click Trading (This Product):**
- Optional enhancement that modifies bottom sheet behavior for market orders from the chart.
- When enabled: Removes confirmation step for market orders.
- When disabled: Bottom sheet works in standard mode (with confirmation).

### Out of Scope for MVP

**Deferred to Future Versions:**

1. **Advanced Order Types** (Limit, Stop orders)
2. **Advanced Order Options** (TP/SL)
3. **Quote Lock System**
4. **Position Awareness**
5. **Order Templates**
6. **Additional Entry Points**
   - **Watchlist integration**
   - **InfoTab integration**
   - **TradeTable integration**
   - **Alert-triggered orders**
7. **Multi-Platform Support** (Web, Desktop)
8. **Advanced Analytics**

### MVP Success Criteria

**Adoption Metrics:**
- 15%+ of eligible users opt-in to one-click trading.

**Usage Metrics:**
- 60%+ of market orders from adopters use the one-click flow from the chart.

**Impact Metrics:**
- 5%+ increase in orders per user for one-click adopters.

**Quality Metrics:**
- No increase in error rates or support tickets.

---

### Future Vision

**Post-MVP Enhancements (v2.0):**
- Additional Order Types (Limit, Stop)
- Advanced Order Options (TP/SL)
- Quote Lock System
- Position Integration
- Platform Expansion (Web, Desktop)
- Additional Entry Points (Chart, Watchlist, etc.)
- Smart Features (Order templates, ML recommendations)