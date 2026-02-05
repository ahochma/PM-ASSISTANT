# Fast Order Component - Product Solution

**Author:** John (PM Agent)  
**Date:** January 12, 2026  
**Status:** Product Solution Document  
**Owner:** Amit Hochma

---

## Executive Summary

**The Core Problem:** We're losing trades at the moment of highest intent. Users click Buy/Sell with clear intent, but 26-28% abandon before submission because we break their focus with unnecessary navigation.

**The Opportunity:** Market research shows industry consensus - every major trading platform uses bottom sheet patterns for mobile order entry. We're behind the curve, and it's costing us conversion.

**The Solution:** A reusable `QuickOrderSheet` component that eliminates context switching while maintaining safety and clarity. This isn't just UI polish - it's a conversion optimization that directly impacts revenue.

**Expected Impact:**
- **Conversion lift:** 15-25% improvement in Buy/Sell → Order submission (based on industry benchmarks)
- **Speed improvement:** 40-60% reduction in time-to-submit (from ~8-12s to ~3-5s)
- **Trade frequency:** 10-20% increase in orders per active trader
- **Revenue impact:** Assuming 20% conversion lift × average order value × current volume = **significant revenue increase**

---

## WHY This Matters: The Deeper Problem

### The User's Moment of Truth

When a trader taps "Buy" or "Sell," they're at peak intent. They've:
- Analyzed the market
- Made a decision
- Committed mentally to the trade

**WHY are we breaking that flow?** Navigation to a new screen is cognitive overhead at the worst possible moment. It's like asking someone to fill out paperwork right as they're about to sign a contract.

### The Data Tells the Story

**Current State:**
- TradeTable → Submit: **72% conversion** (28% abandon)
- InfoTab → Submit: **74% conversion** (26% abandon)

**Industry Benchmark (from research):**
- Robinhood: ~85-90% conversion (estimated from UX patterns)
- Coinbase: ~88-92% conversion
- Binance: ~82-87% conversion

**The Gap:** We're leaving 10-15 percentage points on the table. That's **real money walking away**.

### The Business Impact

**WHY should we care beyond user experience?**

1. **Revenue Impact:** Every abandoned order is lost revenue. If we improve conversion by 20%:
   - Current: 1,000 orders/day × $50 avg commission = $50k/day
   - Improved: 1,200 orders/day × $50 avg commission = $60k/day
   - **Annual impact: $3.65M additional revenue** (assuming 365 trading days)

2. **Competitive Moat:** Every major competitor uses bottom sheets. We look outdated and slow.

3. **User Retention:** Faster, smoother flows = happier users = higher retention = lower CAC.

4. **Trade Frequency:** Active traders trade more when friction is removed. More trades = more revenue.

---

## Product Vision

**Vision Statement:**  
Enable traders to execute orders in under 5 seconds from any screen, without losing context or confidence.

**Product Differentiator:**  
Unlike competitors who built bottom sheets as one-off solutions, we're building a **reusable component** that can be embedded anywhere - TradeTable, InfoTab, Chart, Watchlist, Alerts, etc. This creates a consistent, fast experience across the entire app.

---

## Success Criteria

### Primary Metrics (Must-Have)

1. **Conversion Rate Improvement**
   - **Target:** 20%+ improvement in Buy/Sell → Order submission
   - **Current Baseline:** 72-74%
   - **Target:** 86-89%
   - **Measurement:** A/B test: Control (full screen) vs Variant (bottom sheet)

2. **Time-to-Submit Reduction**
   - **Target:** 50%+ reduction
   - **Current Baseline:** 8-12 seconds
   - **Target:** 3-5 seconds
   - **Measurement:** Analytics event timing

3. **Orders Per Active Trader**
   - **Target:** 15%+ increase
   - **Measurement:** Compare active traders in test vs control groups

### Defensive Metrics (Must Not Degrade)

1. **Error Rate:** Must not increase (target: <1% error rate)
2. **Trade Cancellation Rate:** Must not increase (target: <2% cancellation)
3. **Support Tickets:** Must not increase related to accidental trades
4. **User Trust Signals:** No negative feedback on safety/perceived risk

### Business Metrics

1. **Revenue Per User:** Track impact on ARPU
2. **Retention:** Monitor 30-day retention for test group
3. **Feature Adoption:** % of users who use bottom sheet vs full screen (when both available)

---

## Product Scope

### MVP - Phase 1: Core Component (Weeks 1-4)

**Goal:** Prove the concept works with minimal risk.

**What's In:**
1. **Bottom Sheet Container**
   - Slide-up animation (300-400ms)
   - Swipe-down dismiss
   - Backdrop dimming
   - Draggable handle

2. **Order Entry Core**
   - Side toggle (Buy/Sell) with color coding
   - Symbol display
   - Live price display
   - Order type selection (Market/Limit/Stop)
   - Size selection (percentage chips: 25/50/75/100% + slider)
   - Available balance display
   - Estimated cost/fees calculation

3. **Prefill Intelligence**
   - From TradeTable: Prefill side + price from tapped row
   - From InfoTab: Prefill side from Buy/Sell button
   - Price from current market data

4. **Validation & Submission**
   - Real-time validation
   - Inline error messages
   - Primary CTA: "Place Order"
   - Success state with confirmation

5. **Entry Points**
   - TradeTable → Bottom sheet
   - InfoTab → Bottom sheet

**What's Out (for MVP):**
- Quote lock timer (Phase 2)
- Position display (Phase 2)
- Advanced options (TP/SL) (Phase 2)
- Order templates (Phase 3)
- Other entry points (Phase 2+)

**Success Criteria for MVP:**
- Conversion improvement ≥15%
- Time-to-submit reduction ≥40%
- Error rate ≤1%
- Zero increase in support tickets

---

### Phase 2: Enhanced Features (Weeks 5-8)

**Goal:** Optimize for power users and complex scenarios.

**What's In:**
1. **Quote Lock System**
   - 5-second price lock on sheet open
   - Visual countdown timer
   - Auto-refresh after expiry
   - Haptic feedback

2. **Position Awareness**
   - Current position display
   - P&L indicator
   - Quick actions: "Close Position", "Reverse Position"

3. **Advanced Options (Collapsible)**
   - Take Profit input
   - Stop Loss input
   - Time-in-Force selection
   - Reduce-only toggle

4. **Additional Entry Points**
   - Chart → Bottom sheet (price from crosshair)
   - Watchlist → Bottom sheet
   - Alert → Bottom sheet

5. **Persistent State**
   - Remember last order type per symbol
   - Remember last size (percentage or amount)
   - Per-user preferences

**Success Criteria:**
- Maintain Phase 1 gains
- Power user satisfaction increase
- Complex order completion rate ≥80%

---

### Phase 3: Personalization & Optimization (Weeks 9-12)

**Goal:** Make it feel personalized and learn from usage.

**What's In:**
1. **Order Templates**
   - User-defined templates
   - Quick access to favorites
   - Template sharing (future)

2. **Smart Defaults**
   - ML-based size suggestions
   - Context-aware defaults
   - Usage pattern learning

3. **Accessibility Enhancements**
   - Voice input support
   - Enhanced screen reader support
   - High contrast mode

4. **Analytics & Insights**
   - User behavior tracking
   - A/B test framework
   - Performance monitoring

**Success Criteria:**
- User satisfaction score ≥4.5/5
- Template usage rate ≥30%
- Accessibility compliance (WCAG 2.1 AA)

---

## Functional Requirements

### FR-001: Bottom Sheet Container
**Priority:** P0 (MVP)  
**Description:**  
The component must render as a bottom sheet overlay that slides up from the bottom of the screen, covering 60-80% of viewport height. The sheet must be dismissible via swipe-down gesture or close button.

**Acceptance Criteria:**
- Sheet animates smoothly (300-400ms) on open/close
- Backdrop is dimmed (40-60% opacity) when sheet is open
- Swipe-down gesture dismisses sheet
- Sheet can be dragged to resize (optional, Phase 2)
- Background content remains visible but non-interactive

**Dependencies:** None  
**Risks:** Performance on low-end devices, gesture conflicts

---

### FR-002: Side Selection (Buy/Sell Toggle)
**Priority:** P0 (MVP)  
**Description:**  
Users must be able to select order side (Buy or Sell) via a prominent toggle. The selection must be visually distinct with color coding (green for Buy, red for Sell).

**Acceptance Criteria:**
- Toggle is prominently displayed in header
- Buy side is green, Sell side is red (consistent with app)
- Selection state is clear and persistent
- Toggle can be changed at any time before submission
- Visual feedback on selection change

**Dependencies:** None  
**Risks:** Color blindness accessibility

---

### FR-003: Symbol Display
**Priority:** P0 (MVP)  
**Description:**  
The trading symbol must be clearly displayed in the sheet header, showing what instrument the user is trading.

**Acceptance Criteria:**
- Symbol is displayed prominently
- Full symbol name is visible (e.g., "BTC/USD")
- Symbol cannot be changed within sheet (opens with pre-selected symbol)

**Dependencies:** None  
**Risks:** None

---

### FR-004: Live Price Display
**Priority:** P0 (MVP)  
**Description:**  
Current market price must be displayed and updated in real-time. Price must be clearly visible and formatted according to instrument precision.

**Acceptance Criteria:**
- Price updates in real-time (<1s latency)
- Price is formatted with correct decimal places
- Price display is prominent and readable
- Price source is indicated (e.g., "Last: $45,234.56")

**Dependencies:** Market data feed  
**Risks:** Data latency, stale prices

---

### FR-005: Order Type Selection
**Priority:** P0 (MVP)  
**Description:**  
Users must be able to select order type: Market, Limit, or Stop. Selection must be via clear tabs or pills. Price input must only appear for Limit and Stop orders.

**Acceptance Criteria:**
- Three options: Market, Limit, Stop
- Selection via tabs/pills interface
- Price input field appears only for Limit/Stop
- Default selection is Market (or last used per symbol)
- Visual distinction between order types

**Dependencies:** None  
**Risks:** User confusion between order types

---

### FR-006: Price Input (Limit/Stop Orders)
**Priority:** P0 (MVP)  
**Description:**  
For Limit and Stop orders, users must be able to enter or adjust price. Price must be validated against market price and instrument constraints.

**Acceptance Criteria:**
- Price input field appears for Limit/Stop orders
- Price can be entered manually or adjusted via +/- buttons
- Price is validated in real-time
- Validation errors are displayed inline
- Price is formatted correctly for instrument

**Dependencies:** FR-005  
**Risks:** Price entry errors, validation complexity

---

### FR-007: Size Selection - Percentage Chips
**Priority:** P0 (MVP)  
**Description:**  
Users must be able to quickly select order size using percentage chips: 25%, 50%, 75%, 100% of available balance.

**Acceptance Criteria:**
- Four chips: 25%, 50%, 75%, 100%
- Chips are prominently displayed
- Selection updates order size immediately
- Selected chip is visually highlighted
- Only one chip can be selected at a time

**Dependencies:** Balance calculation  
**Risks:** None

---

### FR-008: Size Selection - Slider
**Priority:** P0 (MVP)  
**Description:**  
Users must be able to fine-tune order size using a slider control. Slider must work in conjunction with percentage chips.

**Acceptance Criteria:**
- Slider allows fine-tuning between 0-100%
- Slider updates when chip is selected
- Chip selection updates when slider is moved
- Slider has visual feedback
- Slider is accessible (keyboard navigation)

**Dependencies:** FR-007  
**Risks:** Precision on small screens

---

### FR-009: Available Balance Display
**Priority:** P0 (MVP)  
**Description:**  
Available trading balance must be prominently displayed, updating in real-time as order size changes.

**Acceptance Criteria:**
- Balance is displayed clearly
- Balance updates in real-time
- Balance format is clear (e.g., "$1,234.56")
- Balance source is indicated (e.g., "Available:")

**Dependencies:** Account balance API  
**Risks:** Stale balance data

---

### FR-010: Estimated Cost/Fees Calculation
**Priority:** P0 (MVP)  
**Description:**  
Estimated total cost (order value + fees) must be calculated and displayed in real-time as user adjusts order parameters.

**Acceptance Criteria:**
- Cost calculation updates in real-time
- Fee breakdown is shown (order value + fees)
- Calculation is accurate
- Display format is clear (e.g., "Est. Cost: $500.00 + $2.50 fee")

**Dependencies:** Fee calculation logic  
**Risks:** Fee calculation complexity, accuracy

---

### FR-011: Prefill from TradeTable
**Priority:** P0 (MVP)  
**Description:**  
When opening sheet from TradeTable, order side and price must be prefilled from the tapped row (bid/ask price).

**Acceptance Criteria:**
- Tapping bid price prefills Sell side + bid price
- Tapping ask price prefills Buy side + ask price
- Prefilled values are clearly indicated
- User can override prefilled values
- Prefill works for both Market and Limit orders

**Dependencies:** TradeTable integration  
**Risks:** Stale price data, user confusion

---

### FR-012: Prefill from InfoTab
**Priority:** P0 (MVP)  
**Description:**  
When opening sheet from InfoTab, order side must be prefilled from the tapped Buy/Sell button.

**Acceptance Criteria:**
- Tapping "Buy" prefills Buy side
- Tapping "Sell" prefills Sell side
- Price is prefilled from current market price
- Prefilled values are clearly indicated
- User can override prefilled values

**Dependencies:** InfoTab integration  
**Risks:** None

---

### FR-013: Real-Time Validation
**Priority:** P0 (MVP)  
**Description:**  
Order inputs must be validated in real-time. Validation errors must be displayed inline, and submit button must be disabled until all validations pass.

**Acceptance Criteria:**
- Validation runs on every input change
- Errors are displayed inline near relevant field
- Error messages are clear and actionable
- Submit button is disabled when errors exist
- Validation covers: balance, price limits, size limits, order type constraints

**Dependencies:** Validation rules  
**Risks:** Performance with frequent validation

---

### FR-014: Order Submission
**Priority:** P0 (MVP)  
**Description:**  
Users must be able to submit orders via a prominent primary CTA. Submission must include confirmation feedback and sheet dismissal.

**Acceptance Criteria:**
- Primary CTA: "Place Order" or contextual "Buy [Amount] [Symbol]"
- CTA is prominently displayed
- CTA is disabled until validation passes
- On submit: Loading state → Success confirmation → Auto-dismiss (2-3s)
- Error handling if submission fails

**Dependencies:** Order submission API  
**Risks:** Network failures, API errors

---

### FR-015: Success Confirmation
**Priority:** P0 (MVP)  
**Description:**  
After successful order submission, users must receive clear confirmation feedback before sheet dismisses.

**Acceptance Criteria:**
- Success message is displayed (e.g., "Order placed successfully")
- Order details are shown in confirmation
- Confirmation is visible for 2-3 seconds
- Sheet auto-dismisses after confirmation
- Optional: Haptic feedback on success

**Dependencies:** FR-014  
**Risks:** None

---

### FR-016: Quote Lock System (Phase 2)
**Priority:** P1 (Phase 2)  
**Description:**  
When sheet opens, price quote must be locked for 5 seconds. Visual countdown timer must indicate remaining lock time. Quote must auto-refresh after expiry.

**Acceptance Criteria:**
- Price is locked for 5 seconds on sheet open
- Countdown timer is visible and clear
- Timer updates every second
- Price refreshes automatically after lock expires
- Haptic feedback when lock expires
- User can manually refresh quote

**Dependencies:** Market data API  
**Risks:** User confusion, API rate limits

---

### FR-017: Position Display (Phase 2)
**Priority:** P1 (Phase 2)  
**Description:**  
If user has an open position in the instrument, position details must be displayed: size, P&L, and quick actions (Close/Reverse).

**Acceptance Criteria:**
- Position pill displays: size, unrealized P&L
- P&L is color-coded (green profit, red loss)
- Quick actions: "Close Position", "Reverse Position"
- Position display is compact and non-intrusive
- Position updates in real-time

**Dependencies:** Position data API  
**Risks:** Information overload

---

### FR-018: Advanced Options (Phase 2)
**Priority:** P1 (Phase 2)  
**Description:**  
Advanced order options (Take Profit, Stop Loss, Time-in-Force, Reduce-Only) must be available in a collapsible section.

**Acceptance Criteria:**
- Advanced section is collapsible
- Options include: TP, SL, TIF, Reduce-Only
- Options are clearly labeled
- Validation applies to advanced options
- Section is hidden by default

**Dependencies:** Order type support  
**Risks:** UI complexity, user confusion

---

## Non-Functional Requirements

### Performance

**NFR-001: Sheet Animation Performance**
- Sheet open/close animation must complete in ≤400ms
- Animation must be smooth (60fps) on mid-range devices
- No jank or stuttering during animation

**NFR-002: Real-Time Updates**
- Price updates must have <1s latency
- Balance updates must have <2s latency
- Updates must not cause UI jank

**NFR-003: Input Responsiveness**
- Input validation must complete in <100ms
- Form interactions must feel instant (<50ms feedback)
- No perceived lag on user actions

---

### Security

**NFR-004: Order Validation**
- All order validations must run server-side
- Client-side validation is for UX only
- No sensitive data in client logs

**NFR-005: Rate Limiting**
- Order submission must respect rate limits
- User must be informed of rate limit violations
- Rate limit errors must be handled gracefully

---

### Accessibility

**NFR-006: WCAG Compliance**
- Component must meet WCAG 2.1 AA standards
- Screen reader support for all interactive elements
- Keyboard navigation support
- High contrast mode support

**NFR-007: Touch Targets**
- All interactive elements must be ≥44×44pt (iOS) / 48×48dp (Android)
- Adequate spacing between touch targets
- No overlapping interactive areas

---

### Usability

**NFR-008: Error Handling**
- All errors must be displayed inline
- Error messages must be clear and actionable
- Error recovery must be intuitive
- No technical jargon in error messages

**NFR-009: Visual Hierarchy**
- Most important information (price, size, CTA) must be most prominent
- Visual hierarchy guides user attention
- No information overload

---

## User Experience Principles

### 1. Speed Over Everything
Every interaction must feel instant. If it takes >100ms, optimize it.

### 2. Context Preservation
Never break user's mental model. Keep them in their flow.

### 3. Progressive Disclosure
Show what's needed, hide what's not. Advanced options are collapsible.

### 4. Error Prevention
Validate early, validate often. Prevent errors before they happen.

### 5. Clear Feedback
Every action needs feedback. Loading states, success states, error states.

### 6. Consistency
Same component, same behavior, everywhere. Build once, use everywhere.

---

## Key Interactions

### Interaction 1: Opening Sheet from TradeTable
1. User taps bid/ask price in table row
2. Sheet slides up (300ms)
3. Side and price are prefilled
4. User adjusts size (if needed)
5. User taps "Place Order"
6. Order submits, confirmation shows, sheet dismisses

**Time Target:** ≤5 seconds total

---

### Interaction 2: Opening Sheet from InfoTab
1. User taps "Buy" or "Sell" button
2. Sheet slides up (300ms)
3. Side is prefilled, price is current market
4. User selects size (chips or slider)
5. User taps "Place Order"
6. Order submits, confirmation shows, sheet dismisses

**Time Target:** ≤5 seconds total

---

### Interaction 3: Complex Order (Limit with TP/SL)
1. User opens sheet (any entry point)
2. User selects "Limit" order type
3. User enters limit price
4. User expands "Advanced Options"
5. User enters Take Profit and Stop Loss
6. User selects size
7. User taps "Place Order"
8. Order submits, confirmation shows, sheet dismisses

**Time Target:** ≤15 seconds total

---

## Risks & Mitigation

### Risk 1: User Confusion / Muscle Memory Disruption
**Impact:** High  
**Probability:** Medium  
**Mitigation:**
- Gradual rollout (10% → 50% → 100%)
- Opt-out option for users who prefer full screen
- User education and onboarding
- Clear visual cues and familiar patterns

---

### Risk 2: Performance on Low-End Devices
**Impact:** Medium  
**Probability:** Medium  
**Mitigation:**
- Performance testing on low-end devices
- Optimize animations and rendering
- Fallback to simpler animations if needed
- Monitor performance metrics

---

### Risk 3: Increased Error Rate
**Impact:** High  
**Probability:** Low  
**Mitigation:**
- Comprehensive validation (client + server)
- Clear error messages
- Confirmation toggle in settings (optional)
- Monitor error rates closely

---

### Risk 4: Regulatory / Compliance Concerns
**Impact:** High  
**Probability:** Low  
**Mitigation:**
- Legal review of UX changes
- Ensure all required disclosures are present
- Maintain audit trail
- Compliance team sign-off

---

### Risk 5: Information Overload in Constrained Space
**Impact:** Medium  
**Probability:** Medium  
**Mitigation:**
- Progressive disclosure (advanced options collapsible)
- Clear visual hierarchy
- User testing with real users
- Iterate based on feedback

---

## Implementation Plan

### Phase 1: MVP (Weeks 1-4)

**Week 1: Foundation**
- Component architecture design
- Bottom sheet container implementation
- Basic layout and styling
- Animation system

**Week 2: Core Functionality**
- Side toggle
- Order type selection
- Size selection (chips + slider)
- Price input (Limit/Stop)
- Balance and cost calculation

**Week 3: Integration**
- TradeTable integration
- InfoTab integration
- Prefill logic
- Validation system

**Week 4: Polish & Testing**
- Error handling
- Success states
- Performance optimization
- QA testing
- User acceptance testing

**Deliverable:** MVP ready for A/B test

---

### Phase 2: Enhanced Features (Weeks 5-8)

**Week 5: Quote Lock**
- Quote lock system
- Timer implementation
- Auto-refresh logic

**Week 6: Position Display**
- Position data integration
- P&L calculation
- Quick actions

**Week 7: Advanced Options**
- Collapsible section
- TP/SL inputs
- TIF and Reduce-Only

**Week 8: Additional Entry Points**
- Chart integration
- Watchlist integration
- Testing and polish

**Deliverable:** Enhanced version ready for rollout

---

### Phase 3: Personalization (Weeks 9-12)

**Week 9-10: Order Templates**
- Template system
- User preferences
- Persistence layer

**Week 11: Smart Defaults**
- ML integration (if applicable)
- Usage pattern analysis
- Context-aware defaults

**Week 12: Accessibility & Analytics**
- Accessibility audit and fixes
- Analytics implementation
- Performance monitoring

**Deliverable:** Full-featured version

---

## Success Measurement Plan

### A/B Test Design

**Test Duration:** 4 weeks  
**Sample Size:** 10,000 users per variant (20,000 total)  
**Split:** 50/50 (Control vs Variant)

**Control Group:**
- Current full-screen order flow
- No changes

**Variant Group:**
- Bottom sheet order flow
- MVP features only

**Metrics Tracked:**
1. Conversion rate (Buy/Sell → Order submission)
2. Time-to-submit
3. Orders per active trader
4. Error rate
5. Support tickets
6. User satisfaction (survey)

**Success Criteria:**
- Conversion improvement ≥15%
- Time-to-submit reduction ≥40%
- No increase in error rate
- No increase in support tickets
- User satisfaction ≥4.0/5.0

---

## Next Steps

### Immediate Actions (This Week)
1. ✅ Market research completed
2. ✅ Product solution document created
3. ⏭️ Stakeholder review and approval
4. ⏭️ Engineering kickoff meeting
5. ⏭️ Design mockup creation

### Short-Term (Next 2 Weeks)
1. Design review and approval
2. Technical architecture design
3. Component API specification
4. A/B test framework setup
5. Analytics event planning

### Medium-Term (Next Month)
1. MVP development start
2. Weekly progress reviews
3. User testing preparation
4. QA test plan creation

---

## Open Questions

1. **Confirmation Toggle:** Should we include a user setting to require confirmation for all orders? (Default: off for speed, but user can enable for safety)

2. **Quote Lock Duration:** Is 5 seconds optimal, or should it be configurable per instrument type?

3. **Position Display:** Should position display be always visible, or only when user has a position?

4. **Advanced Options Default:** Should advanced options be hidden by default, or shown for power users?

5. **Rollout Strategy:** Gradual rollout (10% → 50% → 100%) or all-at-once for A/B test?

---

## References

- Market Research: `market-research-order-submission-ux.md`
- Experiment Document: `FastTrading expirement.md`
- Industry Benchmarks: Robinhood, Coinbase, Binance, TradingView, eToro

---

**Document Status:** Ready for Review  
**Next Review Date:** After stakeholder feedback  
**Owner:** John (PM Agent)  
**Stakeholders:** Amit Hochma, Engineering Lead, Design Lead, QA Lead

---

## Appendix: Component API Specification (Draft)

```typescript
interface QuickOrderSheetProps {
  // Required
  symbol: string;
  onSubmit: (order: OrderPayload) => Promise<void>;
  onClose: () => void;
  
  // Optional Prefill
  prefillSide?: 'buy' | 'sell';
  prefillPrice?: number;
  prefillSize?: number;
  prefillMode?: 'market' | 'limit' | 'stop';
  
  // Configuration
  entryPoint: 'table' | 'info' | 'chart' | 'watchlist';
  showPosition?: boolean;
  showAdvanced?: boolean;
  
  // Callbacks
  onOrderTypeChange?: (type: OrderType) => void;
  onSizeChange?: (size: number) => void;
  onPriceChange?: (price: number) => void;
}

interface OrderPayload {
  symbol: string;
  side: 'buy' | 'sell';
  type: 'market' | 'limit' | 'stop';
  size: number;
  price?: number;
  takeProfit?: number;
  stopLoss?: number;
  timeInForce?: string;
  reduceOnly?: boolean;
}
```

---

_This product solution document represents a comprehensive plan to solve the fast order submission problem. It's data-driven, risk-aware, and focused on measurable business impact. Let's build something great._ 🚀
