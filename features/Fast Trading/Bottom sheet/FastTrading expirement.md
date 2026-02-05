# Fast Trading Experiment
## Trade Screen as Bottom Sheet (Mobile)

**Owner:** Amit Hochma  
**Status:** Experiment  
**Platforms:** Mobile (iOS / Android)  
**Date:** January 12, 2026  
**Related Documents:**
- Market Research: `market-research-order-submission-ux.md`
- Product Solution: `fast-order-component-product-solution.md`

---

## 1. Background

Fast trading on mobile is a critical part of the trading experience. Today, when users tap Buy or Sell, they are navigated to a separate trade screen and losing context. This navigation creates a context switch, slows the flow, and breaks user focus at the moment of highest intent.

**Current Performance Data:**
- TradeTable → Submit order: **72% conversion** (28% abandon rate)
- InfoTab → Submit order: **74% conversion** (26% abandon rate)
- Average time-to-submit: **8-12 seconds**


Data and user feedback show that most users open market orders and want to enter the market immediately. This behavior is consistent across all user segments, including premium and highly active traders.

**Market Research Insight:** Every major trading platform (Robinhood, Coinbase, Binance, eToro, TradingView) uses bottom sheet patterns for mobile order entry. This is industry consensus, not experimental.

---

## 2. Problem Statement

The current mobile trade flow introduces unnecessary friction at the point of execution, costing us conversion and revenue.

**Key Issues:**
1. **Context Switching:** Users are redirected to a new screen after expressing clear intent, breaking focus from analysis or price movement
2. **Perceived Speed:** The flow feels slower than expected (8-12s), especially during volatile moments when speed matters most
3. **Conversion Loss:** 26-28% of users abandon before submission - this is lost revenue
4. **Competitive Disadvantage:** We're behind industry standards - competitors achieve 10-15% higher conversion rates

**Business Impact:**
- Every abandoned order is lost revenue
- Slower flows reduce trade frequency for active traders
- Outdated UX hurts brand perception and user retention
- Estimated revenue opportunity: **$3.65M annually** with 20% conversion improvement



## 3. Experiment Goal

**Primary Goal:**  
Reduce friction at the trade entry point by removing screen navigation, while keeping the trade experience safe, clear, and familiar.

**Specific Objectives:**
1. **Conversion Improvement:** Achieve 15-25% improvement in Buy/Sell → Order submission conversion rate
2. **Speed Improvement:** Reduce time-to-submit by 40-60% (from 8-12s to 3-5s)
3. **Trade Frequency:** Increase orders per active trader by 10-20%
4. **Zero Regression:** Maintain or improve error rates, cancellation rates, and user trust

**Success Threshold:**  
Experiment is successful if we achieve ≥15% conversion improvement AND ≥40% time reduction WITHOUT increasing error rates or support tickets.

---

## 4. Hypothesis

**Primary Hypothesis:**  
If we present the existing trade screen as a bottom sheet instead of a full screen, users will submit trades faster and more often, because they stay in context and perceive the flow as quicker.

**Supporting Evidence:**
- Industry consensus: All major competitors use bottom sheets (market research)
- UX principle: Context preservation reduces cognitive load
- Mobile pattern: Bottom sheets are familiar iOS/Android pattern
- Prefill intelligence: Can leverage user intent (tapped bid/ask) to reduce input steps

**Expected Outcomes:**
- **Conversion:** 72-74% → 86-89% (20%+ improvement)
- **Time:** 8-12s → 3-5s (50%+ reduction)
- **Frequency:** 10-20% increase in orders per active trader

---

## 5. Main Flows in Scope

The experiment focuses on two high-intent entry points that represent **~73% of all order submissions**:

1. **TradeTable → Submit order (~72% of orders)**
   - Entry: Tap bid/ask price in table row
   - Prefill: Side + price from tapped row
   - Context: Table remains visible behind sheet

2. **InfoTab → Submit order (~74% of orders)**
   - Entry: Tap Buy/Sell button
   - Prefill: Side from button, price from market data
   - Context: Chart and info remain visible behind sheet

**Out of Scope (for MVP):**
- Chart → Submit order (Phase 2)
- Watchlist → Submit order (Phase 2)
- Alert → Submit order (Phase 2)
- All other entry points remain unchanged during experiment

## 6. Experiment Design

### A/B Test Structure

**Test Duration:** 4 weeks  
**Sample Size:** 10,000 users per variant (20,000 total)  
**Split:** 50/50 (Control vs Variant)  
**Randomization:** Random assignment at user level (sticky assignment)

### Variant A (Control)
- **Current State:** Buy/Sell opens trade screen as full new screen
- **Navigation:** Full-screen navigation (current behavior)
- **Context:** User leaves current screen completely
- **No Changes:** All existing functionality remains identical

### Variant B (Test)
- **New Behavior:** Buy/Sell opens trade screen as bottom sheet overlay
- **Navigation:** No screen navigation - overlay on current screen
- **Context:** Background screen remains visible (dimmed)
- **Key Features:**
  - Bottom sheet slides up from bottom (60-80% screen height)
  - Swipe-down gesture to dismiss
  - Prefill intelligence:
    - TradeTable: Side + price from tapped bid/ask
    - InfoTab: Side from Buy/Sell button + current market price
  - Same trade fields, logic, and validations
  - Same order types and risk management tools
  - Smooth animations (300-400ms)

**Critical Constraint:**  
The experiment changes **presentation only, not functionality**. All order logic, validations, risk management, and business rules remain identical. This isolates the effect of context switching removal.

## 7. Visual and UX Elements to Validate

We want to validate the following visual and interaction aspects based on industry best practices:

### Core UX Elements
1. **Bottom Sheet Behavior**
   - Slide-up animation smoothness (300-400ms target)
   - Swipe-down dismiss gesture responsiveness
   - Backdrop dimming (40-60% opacity)
   - Sheet height (60-80% viewport)
   - Draggable handle (optional, Phase 2)

2. **Perceived Speed**
   - Time-to-first-interaction (<500ms)
   - Animation smoothness (60fps on mid-range devices)
   - Input responsiveness (<100ms feedback)
   - Overall flow completion time (target: 3-5s)

3. **Information Clarity**
   - Price visibility and prominence
   - Size selection clarity (chips + slider)
   - Balance and cost display
   - Order type distinction (Market/Limit/Stop)
   - Visual hierarchy guides attention

4. **User Confidence**
   - Clear validation feedback
   - Inline error messages
   - Success confirmation
   - Trust signals (balance, fees, order details)

5. **Accessibility**
   - Touch targets ≥44×44pt (iOS) / 48×48dp (Android)
   - Screen reader support
   - Keyboard navigation
   - High contrast mode
   - WCAG 2.1 AA compliance

6. **Prefill Intelligence**
   - Visual indication of prefilled values
   - Ability to override prefilled values
   - Context-aware defaults

**Validation Goal:**  
Ensure the experience feels faster without reducing clarity or trust. Validate against industry benchmarks from Robinhood, Coinbase, and Binance.

## 8. User Groups and Segmentation

Results will be analyzed by the following groups to identify segment-specific patterns:

### Primary Segmentation (Must Analyze)

1. **Trading Activity Level**
   - **Active traders:** High trade frequency (>10 orders/week)
   - **Regular traders:** Medium frequency (3-10 orders/week)
   - **Casual traders:** Low frequency (<3 orders/week)
   - **Hypothesis:** Active traders will benefit most from speed improvements

2. **User Tier**
   - **Premium users:** Paid subscription tier
   - **Regular retail users:** Free tier
   - **Hypothesis:** Premium users may have higher expectations for UX quality

3. **User Tenure**
   - **New users:** <30 days since first trade
   - **Returning users:** >30 days since first trade
   - **Hypothesis:** New users may prefer familiar full-screen pattern

### Secondary Segmentation (Analyze if Sample Size Allows)

1. **Trading Conditions**
   - High volatility periods (market events, news)
   - Normal trading conditions
   - **Hypothesis:** Speed matters more during volatility

2. **Instrument Type**
   - High-volume instruments (major pairs, popular stocks)
   - Low-volume instruments (exotic pairs, small-cap stocks)
   - **Hypothesis:** High-volume instruments may show stronger effects

3. **Order Type**
   - Market orders (simple, fast)
   - Limit/Stop orders (complex, slower)
   - **Hypothesis:** Bottom sheet may work better for market orders

4. **Device Type**
   - iOS vs Android
   - Screen size (small vs large)
   - **Hypothesis:** Platform-specific UX patterns may differ

### Analysis Approach

- **Primary Analysis:** Overall test vs control comparison
- **Segment Analysis:** Compare results within each segment
- **Interaction Effects:** Identify if certain segments benefit more/less
- **Decision Rule:** If segment shows negative results, consider excluding from rollout

## 9. Success Metrics

### Primary Metrics (Must Achieve)

1. **Conversion Rate Improvement**
   - **Metric:** Conversion rate from Buy/Sell click → Order submission
   - **Current Baseline:** 72-74% (TradeTable: 72%, InfoTab: 74%)
   - **Target:** 86-89% (20%+ improvement)
   - **Minimum Success:** ≥15% improvement (≥83% conversion)
   - **Measurement:** A/B test comparison, statistical significance (p<0.05)

2. **Time-to-Submit Reduction**
   - **Metric:** Time from Buy/Sell click → Order submission
   - **Current Baseline:** 8-12 seconds
   - **Target:** 3-5 seconds (50%+ reduction)
   - **Minimum Success:** ≥40% reduction (≤7.2s)
   - **Measurement:** Analytics event timing (start → submit)

3. **Orders Per Active Trader**
   - **Metric:** Average orders per active trader (weekly)
   - **Target:** 15%+ increase
   - **Minimum Success:** ≥10% increase
   - **Measurement:** Compare active traders in test vs control groups

### Defensive Metrics (Must Not Degrade)

1. **Error Rate**
   - **Current Baseline:** <1%
   - **Target:** ≤1% (no increase)
   - **Measurement:** Invalid submissions, validation failures

2. **Trade Cancellation Rate**
   - **Current Baseline:** <2%
   - **Target:** ≤2% (no increase)
   - **Measurement:** Orders cancelled within 5 minutes of submission

3. **Support Tickets**
   - **Current Baseline:** <0.5% of orders
   - **Target:** ≤0.5% (no increase)
   - **Measurement:** Support tickets related to accidental trades, confusion, or order issues

4. **User Trust Signals**
   - **Target:** No negative feedback on safety/perceived risk
   - **Measurement:** User surveys, app store reviews, NPS scores

### Business Metrics (Track for Context)

1. **Revenue Per User (ARPU)**
   - Track impact on average revenue per user
   - Expected: Positive correlation with conversion improvement

2. **Retention**
   - Monitor 30-day retention for test group
   - Expected: Neutral or positive impact

3. **Feature Adoption**
   - % of users who use bottom sheet vs full screen (if both available)
   - Expected: High adoption rate (>70%)

---

## 10. What Success Looks Like

The experiment is considered **successful** if we achieve:

### Must-Have Criteria (All Required)
- ✅ **Conversion improvement ≥15%** (72-74% → ≥83%)
- ✅ **Time reduction ≥40%** (8-12s → ≤7.2s)
- ✅ **Error rate ≤1%** (no increase)
- ✅ **Cancellation rate ≤2%** (no increase)
- ✅ **Support tickets ≤0.5%** (no increase)
- ✅ **No negative trust signals** (surveys, reviews)

### Ideal Success (Stretch Goals)
- 🎯 **Conversion improvement ≥20%** (72-74% → 86-89%)
- 🎯 **Time reduction ≥50%** (8-12s → 3-5s)
- 🎯 **Orders per trader increase ≥15%**
- 🎯 **User satisfaction score ≥4.0/5.0**

### Statistical Significance
- Results must be statistically significant (p<0.05)
- Sample size must be sufficient (10k users per variant)
- Results must be consistent across user segments

---

## 11. Next Steps if the Experiment Succeeds

### Immediate Actions (Week 1 after results)
1. **Stakeholder Review**
   - Present results to leadership
   - Review business impact (revenue, conversion, retention)
   - Get approval for full rollout

2. **Gradual Rollout Plan**
   - Week 1-2: Expand to 25% of users
   - Week 3-4: Expand to 50% of users
   - Week 5-6: Expand to 100% of users
   - Monitor metrics at each stage

### Short-Term Enhancements (Weeks 2-8)
1. **Extend Entry Points**
   - Chart → Bottom sheet (price from crosshair)
   - Watchlist → Bottom sheet
   - Alert → Bottom sheet

2. **Enhanced Features (Phase 2)**
   - Quote lock system (5-second price lock with timer)
   - Position display (current position + P&L + quick actions)
   - Advanced options (TP/SL, TIF, Reduce-Only) in collapsible section

3. **Optimization**
   - Analyze usage patterns
   - Optimize defaults based on data
   - A/B test variations (sheet height, animation speed, etc.)

### Medium-Term Improvements (Weeks 9-12)
1. **Order Templates**
   - User-defined templates
   - Quick access to favorites
   - Smart defaults based on history

2. **Personalization**
   - ML-based size suggestions
   - Context-aware defaults
   - Usage pattern learning

3. **Foundation for Future**
   - Use as foundation for other fast trading improvements
   - Apply pattern to other high-intent flows
   - Build reusable component library

---

## 12. What We Do if the Experiment Does Not Succeed

### Analysis Phase (Week 1 after results)

If results are neutral or negative, conduct deep analysis:

1. **Drop-Off Analysis**
   - Identify exact drop-off points inside bottom sheet
   - Analyze user journey: Where do users abandon?
   - Review session recordings and heatmaps

2. **UX Evaluation**
   - Check if layout feels too dense or unclear
   - Validate information hierarchy
   - Test with real users (usability testing)

3. **Segment Analysis**
   - Evaluate results by user segment:
     - Active traders vs casual traders
     - Premium vs regular users
     - New vs returning users
     - High volatility vs normal conditions
   - Identify if certain segments should be excluded

4. **Trust & Safety Review**
   - Review support tickets for patterns
   - Analyze error types and frequency
   - Evaluate user feedback on safety/perceived risk

### Possible Actions (Based on Analysis)

**Option 1: Segment-Specific Rollout**
- Limit feature to active traders only (if they show positive results)
- Keep full screen for casual/new users
- Gradual expansion based on segment performance

**Option 2: Hybrid Approach**
- Use bottom sheet for simple orders (Market orders)
- Use full screen for complex orders (Limit/Stop with TP/SL)
- Let users choose preference in settings

**Option 3: Iterate & Retest**
- Fix identified issues (layout, density, clarity)
- Improve UX based on feedback
- Re-run experiment with improvements

**Option 4: Revert**
- Revert to full screen for all flows
- Document learnings for future experiments
- Consider alternative approaches

**Option 5: Stop Experiment**
- **Only if:** Trust or safety is impacted
- **Only if:** Error rates increase significantly
- **Only if:** Support tickets spike
- Immediate revert required

### Decision Framework

| Scenario | Action |
|----------|--------|
| Conversion <10% improvement | Analyze drop-offs, iterate, or consider segment-specific rollout |
| Conversion 10-15% improvement | Consider hybrid approach or segment-specific rollout |
| Error rate >1% | Fix validation issues, retest |
| Support tickets spike | Immediate analysis, possible revert |
| Trust signals negative | Stop experiment, revert, investigate |
| Neutral results (no improvement) | Deep analysis, consider alternative approaches |

---

## 13. Risks and Considerations

### Why This Might Work

1. **Matches User Intent**
   - Users want fast execution - bottom sheet removes friction
   - Industry consensus validates the approach (all competitors use it)

2. **Removes Friction**
   - Eliminates unnecessary navigation
   - Reduces cognitive load through context preservation
   - Prefill intelligence reduces input steps

3. **Business Impact**
   - Brings customers faster to market
   - Keeps users focused on price and analysis
   - Potential for significant revenue increase ($3.65M annually)

4. **Low Risk**
   - Only UI changes, no functional changes
   - Can revert quickly if needed
   - A/B test isolates the effect

### Why This Might Not Work

1. **User Preferences**
   - Some users prefer full screen for confidence
   - Muscle memory disruption - users already know current flow
   - Bottom sheet can feel less "serious" for high-stakes trades

2. **UX Constraints**
   - Bottom sheet may feel constrained for complex orders
   - Risk management tools may be harder to notice
   - Information density concerns in smaller space

3. **External Factors**
   - Regulation and localized culture might impact results
   - Platform-specific UX patterns (iOS vs Android)
   - Device-specific constraints (small screens)

### Mitigation Strategies

1. **Careful Rollout**
   - Gradual expansion (25% → 50% → 100%)
   - Monitor metrics at each stage
   - Quick revert capability

2. **Clear UI Design**
   - Follow industry best practices (Robinhood, Coinbase patterns)
   - Progressive disclosure (advanced options collapsible)
   - Clear visual hierarchy

3. **Close Monitoring**
   - Real-time analytics dashboard
   - Support ticket monitoring
   - User feedback collection

4. **User Control**
   - Optional confirmation toggle in settings
   - Hybrid approach option (bottom sheet for simple, full screen for complex)
   - Opt-out mechanism if needed

5. **Testing & Validation**
   - Usability testing before launch
   - A/B test with sufficient sample size
   - Segment-specific analysis

**Critical Constraint:**  
We start with only UI component changes, not functional ones. All functionalities remain the same. This isolates the effect and minimizes risk.

---

## 14. Summary

This experiment tests a **low-risk UI change with potentially high impact**. By keeping the trade logic identical and changing only the presentation, we can isolate the effect of removing context switching and make a clear decision based on data.

### Key Points

- **Problem:** 26-28% abandonment at moment of highest intent due to context switching
- **Solution:** Bottom sheet overlay (industry-standard pattern) with prefill intelligence
- **Expected Impact:** 15-25% conversion improvement, 40-60% time reduction
- **Risk Level:** Low (UI-only changes, quick revert capability)
- **Success Criteria:** ≥15% conversion improvement AND ≥40% time reduction WITHOUT regression

### Industry Context

This is **not experimental** - it's industry consensus. Every major trading platform (Robinhood, Coinbase, Binance, eToro, TradingView) uses bottom sheets for mobile order entry. We're catching up, not innovating.

### Decision Framework

- **Success:** Gradual rollout → Enhanced features → Personalization
- **Partial Success:** Segment-specific rollout or hybrid approach
- **Failure:** Deep analysis → Iterate & retest OR revert

**Bottom Line:**  
If we achieve our success criteria, this could unlock **$3.65M+ in annual revenue** through improved conversion. The risk is minimal, the reward is significant, and the approach is validated by industry leaders.
