# Swap-Free Charging Model - Product Concept

**Version:** 2.1 (Updated - Position Size-Based Bin Model)  
**Date:** January 2025  
**Status:** Proposal for Review  
**Based on:** Market research of UAE swap-free models + Internal trading team analysis

---

## Executive Summary

We currently absorb the cost of holding leveraged positions overnight for Swap-Free (Islamic) customers with no direct monetization, creating a revenue gap compared to standard accounts. This proposal introduces a compliant, position size-based administrative fee model with 5 bins that generates incremental revenue while remaining competitive with market standards and fair to users.

**Key Strategy:** Position size-based 5-bin fee structure with dynamic bin assignment, fees deducted from equity (not balance), and whitelist capability for specific users. Compliant with Islamic finance principles.

---

## 1. Problem Statement

### Current State
- Swap-Free customers can hold leveraged positions overnight without any cost
- We absorb all funding costs for these positions with zero revenue offset
- This creates a material revenue gap compared to:
  - Standard accounts (which pay overnight funding)
  - Market competitors (who charge administrative/financing fees)

### Problem Impact

**Business Impact:**
- Direct revenue loss on all swap-free positions held overnight
- No monetization mechanism despite operational costs
- Competitive disadvantage (competitors monetize via compliant fee structures)

**Quantitative Context (from Trading Team Analysis):**
- Most positions opened for >7 days close within 30 days (~75%)
- Majority of positions are relatively small in notional value
- Fixed daily fees can create very high implied annual costs for small positions (risk of churn)

**Market Context:**
- UAE market leaders (eToro, TMGM, Taurex) all monetize swap-free accounts via administrative/financing fees
- Industry standard is 7-14 day grace periods followed by tiered fees
- Regulatory frameworks (DFSA, SCA) permit administrative fees as long as they're transparent and non-interest-based

---

## 2. Product Goals & Success Criteria

### Primary Goals

1. **Generate Incremental Revenue**
   - Monetize swap-free positions via position size-based fee structure
   - Target: Capture revenue opportunity while maintaining competitive positioning

2. **Maintain Market Competitiveness**
   - Align with market standards (7 - day grace period, administrative fees, tiered structures)
   - Avoid introducing churn due to non-competitive pricing

3. **Ensure Compliance**
   - Frame fees as administrative/custody fees (not interest/riba)
   - Maintain full Sharia compliance and regulatory alignment
   - Position size-based model avoids time-based interest perception

4. **Fairness & Transparency**
   - Link costs to position size (fair alignment with exposure)
   - Dynamic bin assignment reflects position size changes
   - Clear, upfront disclosure of all fees and bin structure

5. **Flexibility & Control**
   - Whitelist capability for strategic customer management
   - Ability to exclude specific users from fees when needed

### Success Criteria (v1 Launch)

**Business Metrics:**
- Revenue capture from position size-based fee structure on positions held > 7 days
- Churn rate within 5% of baseline (no material impact)
- Fee collection efficiency >95%

**Competitive Metrics:**
- Grace period aligned with market (7 days for small positions)
- Fee structure competitive with market (Equiti, eToro, TMGM reference benchmarks)
- User feedback: Fees perceived as fair and transparent
- Bin structure provides appropriate differentiation



---

## 3. Market Research & Competitive Analysis

### Competitive Landscape (UAE Market)

| Broker | Free Period | Position Size Limit | Fee After Free Period | Special Rules |
|--------|-------------|---------------------|----------------------|---------------|
| **eToro** | 7 days | No clear limit | Daily admin fee (varies by instrument) | Fixed fees, transparent disclosure |
| **Equiti** | 7 days | No clear limit | Daily admin fee | Triple fee on Wednesday |
| **Taurex** | 30 days | No limit | Fees after 30 days | Extended grace period (competitive differentiator) |
| **TMGM** | Variable | No limit | $10/lot for commodities; variable for others | Instrument-specific fees |
| **ADSS** | Up to 14 days | Up to 3 lots | Standard swap applies | Hard cap on size and time |
| **Alphaex Trade** | 3 days | No limit | Flat admin fee after 3 days | Shortest grace period |
| **Capital.com** | No free period | No limit | Cost via wider spreads | Futures & crypto only |

### Key Market Insights

1. **Grace Period Standard:** 7 days is market standard (Equiti, eToro); 30 days is competitive differentiator (Taurex)
2. **Fee Structure Patterns:**
   - Administrative fees (not interest-based) are standard
   - Tiered fees by time period are common
   - Position-size differentiation exists but is less common
3. **Compliance Approach:** All fees framed as "administrative," "custody," or "financing" fees (not swaps/interest)
4. **Transparency:** Regulatory emphasis on clear fee disclosure

### Market Positioning Strategy

**Our Approach vs. Market:**
- **Grace Period:** 7 days for all positions (aligned with market leaders eToro/Equiti)
- **Differentiation:** 5-bin position size-based structure (more granular than single-tier models)
- **Fee Structure:** Position size-based bins only (no time-based tiers, simpler than competitors)
- **Compliance:** Administrative/custody fees (standard market practice)

**Competitive Advantage:**
- More granular fee structure (5 bins) than single-tier competitors
- Position size-based pricing (fair alignment with exposure)
- No time-based tiers (simpler calculation than time-tiered models)
- Clear bin structure reduces complexity vs. instrument-specific models (e.g., TMGM)

---

## 4. Proposed Solution (v2 - Position Size-Based Bin Model)

### 4.1 Model Overview

**Core Mechanism:** Grace Period + Position Size-Based 5-Bin Administrative Fee Model

- **Fee Type:** Administrative/custody fees (not interest-based, fully Sharia-compliant)
- **Calculation Basis:** Position size (determines bin assignment)
- **Fee Application:** Daily fees deducted from equity (not balance)
- **Compliance Framing:** "Administrative/custody fee for maintaining open positions"
- **Dynamic Assignment:** Customers move between bins as position size changes
- **Note:** Equity = balance + unrealized profit and loss (used for fee deduction, not calculation)

### 4.2 Fee Structure: 5 Position Size-Based Bins

**Bin Assignment:** Based on position size (total notional value of open positions)

| Bin | Position Size Range | Daily Fee per Lot (USD) | Notes |
|-----|---------------------|-------------------------|-------|
| **Bin 1** | $0 - $X | $TBD | Lowest position size tier |
| **Bin 2** | $X - $Y | $TBD | Lower-mid position size tier |
| **Bin 3** | $Y - $Z | $TBD | Mid position size tier |
| **Bin 4** | $Z - $A | $TBD | Upper-mid position size tier |
| **Bin 5** | $A+ | $TBD | Highest position size tier |

**Design Decisions Needed:**
- Exact position size thresholds for each bin (X, Y, Z, A values)
- Fee amounts for each bin (TBD values)
- Fee calculation basis (per lot, per position, or percentage-based)

### 4.3 Key Design Principles

1. **Position size-Based Bin Assignment**
   - Fee calculated based on position size when opened
   - Real-time or daily position size calculation
   - Bin assignment updates as position size change (daily job)

2. **Dynamic Bin Movement**
   - Customers move between bins as position size changes
   - Fees adjust immediately when bin changes (or on next calculation cycle)
   

3. **Equity-Based Fee Deduction**
   - Fees deducted from equity (not balance)
   - Equity = balance + unrealized profit and loss
   - Fee calculation is based on position size, but payment is from equity

4. **No Time Dimension**
   - 7 days grace period
   - No time-based fee tiers
   - Simpler calculation logic
   - Fees apply consistently based on position size bin only

5. **Whitelist Capability**
   - Per-user-ID whitelist
   - Whitelisted users: No fees applied
   - Management interface for whitelist administration

---

## 5. Why This Approach (Rationale)

### 5.1 Position Size-Based Pricing
- **Fairness:** Fees based on position size reflect exposure and risk
- **Dynamic Alignment:** Fees adjust as position size changes (more equitable)
- **Risk-Based:** Larger positions typically have higher risk exposure

### 5.2 Simplicity & Clarity
- **7-Day Grace Period:** Protects short-term traders (market standard)
- **Clear Bin Structure:** 5 bins provide granularity without excessive complexity
- **Predictable:** Users understand their bin and fee level based on position size

### 5.3 Technical & Operational Feasibility
- **Dynamic Bin Assignment:** Daily position size calculation determines bin
- **Flexible System:** Whitelist capability allows for exceptions and special cases
- **Equity-Based Payment:** Fees deducted from equity (balance + unrealized P/L), not balance

### 5.4 Business Strategy
- **Revenue Generation:** Fees based on position size capture value appropriately
- **Scalable Pricing:** 5-bin structure allows for sophisticated pricing tiers
- **Flexibility:** Whitelist enables strategic customer management
- **Measurable & Adjustable:** Bin structure allows for data-driven optimization

### 5.5 Compliance & Regulatory
- **Fee Framing:** Administrative/custody fees (not interest/riba)
- **Transparency:** Clear bin structure and position size-based calculation meets regulatory requirements (DFSA, SCA)
- **Sharia Compliance:** Fees structured to avoid interest classification
- **Equity Payment Model:** Fees deducted from equity (including unrealized P/L) ensures payment capability

---

## 6. Open Questions & Decisions Required

### Critical Decisions (Before Launch)

1. **Bin Position Size Thresholds**
   - **Decision Needed:** Exact position size ranges for 5 bins
   - **Considerations:**
     - User position size distribution analysis
     - Fair differentiation between bins
     - Operational simplicity
   - **Example Structure Needed:**
     - Bin 1: $0 - $X
     - Bin 2: $X - $Y
     - Bin 3: $Y - $Z
     - Bin 4: $Z - $A
     - Bin 5: $A+

2. **Fee Amounts per Bin**
   - **Decision Needed:** Fee per lot for each of the 5 bins
   - **Considerations:**
     - Cost analysis (funding costs vs. fee revenue)
     - Competitive benchmarking (Equiti, eToro, TMGM)
     - Revenue targets



4. **Bin Assignment Frequency**
   - **Question:** How often is position size calculated and bin assignment updated?
   - **Options:** Daily (end of day), real-time, or hybrid
   - **Decision Needed:** Timing of position size calculation and bin reassignment

5. **Bin Transition Handling**
   - **Question:** How to handle bin changes when position size changes?
   - **Options:** Immediate fee adjustment, next-day application, pro-rated fees
   - **Decision Needed:** Rules for bin transitions and fee application timing

6. **Whitelist Management**
   - **Question:** Who can manage whitelist? What's the process?
   - **Decision Needed:** 
     - Whitelist management workflow
     - Approval process
     - Review/renewal process
     - User interface/API requirements

7. **Negative Equity Handling**
   - **Question:** How to handle negative equity scenarios?
   - **Decision Needed:** 
     - Bin assignment rules for negative equity
     - Fee application rules for negative equity

8. **UI/UX Display**
   - **Question:** How are fees displayed in UI?
     - Current bin display?
     - Fee amount display?
     - Equity threshold information?
   - **Decision Needed:** Design specifications for transparency

---

## 7. Risks & Mitigations

### 7.1 Business Risks

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| **Higher cost perception for low-equity users** | High churn, negative feedback | Medium | Clear upfront disclosure; start with conservative pricing; appropriate bin threshold design |
| **Churn impact hard to predict** | Revenue loss from churned customers | High | Start conservative (lower fees); monitor closely; A/B test if possible; rapid iteration based on data |
| **Non-competitive pricing** | Competitive disadvantage, churn | Medium | Benchmark against market leaders (Equiti, eToro, TMGM); monitor competitive moves |
| **Revenue targets not met** | Business goal miss | Medium | Start with conservative fees, iterate based on data; adjust bin thresholds if needed |
| **Bin threshold volatility** | User confusion, support burden | Medium | Clear bin structure communication; stable thresholds; transparent fee calculation based on position size |

### 7.2 Compliance & Regulatory Risks

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| **Fee structure perceived as interest (riba)** | Compliance violation, reputational damage | Low | Frame as administrative/custody fees; avoid interest-rate linkage; legal/compliance review before launch |
| **Regulatory scrutiny on transparency** | Regulatory action, fines | Low | Clear, upfront fee disclosure; align with DFSA/SCA guidelines; compliance review |
| **User complaints about compliance** | Support burden, reputational risk | Medium | Clear communication framing; FAQ addressing compliance; support team training |

### 7.3 Operational Risks

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| **Fee calculation errors** | Revenue loss, user complaints | Low | Rigorous testing; audit calculations; monitoring/alerts |
| **UI/UX confusion about fees** | Support tickets, user frustration | Medium | Clear UI design; user testing; comprehensive FAQ; support training |
| **System integration complexity** | Launch delays, bugs | Medium | Technical assessment early; phased rollout; robust testing |

### 7.4 Market Risks

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| **Competitors change pricing** | Competitive disadvantage | Medium | Monitor competitive landscape; flexible pricing model; rapid adjustment capability |
| **Market shifts to longer grace periods** | Competitive disadvantage | Low | Market research shows 7 days is standard; Taurex 30-day is outlier, not trend |

---

## 8. Validation & Launch Strategy

### 8.1 Pre-Launch Validation

**Internal Validation:**
- [ ] Cost analysis: Funding costs vs. proposed fee revenue
- [ ] Competitive benchmarking: Fee comparison with Equiti, eToro, TMGM
- [ ] Legal/compliance review: Fee structure compliance with Islamic finance principles
- [ ] Technical feasibility: Fee calculation and integration complexity
- [ ] Revenue modeling: Projected revenue impact under different scenarios

### 8.2 Launch Approach

**Phased Rollout (Recommended):**
1. **Phase 1: Communication (30-60 days before launch)**
   - Advance notice to existing customers
   - Clear explanation of fees, rationale, and compliance
   - FAQ and support resources

2. **Phase 2: Soft Launch (if possible)**
   - Limited rollout (e.g., new customers only)
   - Monitor metrics (churn, support tickets, revenue)
   - Rapid iteration based on feedback

3. **Phase 3: Full Launch**
   - All swap-free accounts
   - Ongoing monitoring and adjustment

**Alternative: Full Launch**
- If phased rollout not feasible, full launch with:
  - Advance communication (30+ days)
  - Comprehensive support resources
  - Close monitoring and rapid adjustment capability

### 8.3 Success Metrics & Monitoring

**Week 1-2 (Immediate Impact):**
- Churn rate vs. baseline
- Support ticket volume (fee-related)
- Revenue capture (fees collected)

**Month 1-3 (Short-term):**
- Churn trend (is it stabilizing?)
- Revenue targets (on track?)
- User feedback (surveys, support sentiment)
- Competitive positioning (any competitor moves?)

**Month 3-6 (Medium-term):**
- Fee structure optimization (adjust fees based on data?)
- Revenue sustainability
- Long-term churn impact
- Market positioning (competitive assessment)

---

## 9. Whitelist Functionality

### Overview
- Per-user-ID whitelist capability
- Whitelisted users are exempt from swap-free administrative fees
- Management interface required for whitelist administration

### Implementation Requirements

1. **Data Structure**
   - User ID (primary key)
   - Whitelist status (active/inactive)
   - Added date
   - Added by (administrator)
   - Reason (optional)
   - Expiry date (optional)

2. **Functionality**
   - Add user to whitelist
   - Remove user from whitelist
   - Query whitelist status
   - Audit trail for whitelist changes

3. **Integration**
   - Fee calculation engine checks whitelist before applying fees
   - Whitelist check takes precedence over bin assignment
   - Performance optimization for whitelist queries

4. **Management Interface**
   - Admin interface for whitelist management
   - Search/filter capabilities
   - Bulk operations (if needed)
   - Export/audit capabilities

---

## 10. Future Considerations (Post-v2)

### Potential Enhancements (Based on v2 Learnings)

1. **Bin Threshold Optimization**
   - Adjust bin thresholds based on user distribution data
   - Optimize for revenue and user experience

2. **Fee Amount Optimization**
   - Adjust fee amounts per bin based on performance data
   - Competitive positioning adjustments

3. **Instrument-Specific Fees**
   - Different fees for forex, commodities, indices (if cost/competitive analysis supports)
   - Per-instrument bin structure (if beneficial)

4. **Advanced Whitelist Rules**
   - Time-based whitelist (temporary exemptions)
   - Conditional whitelist rules
   - Automatic whitelist management (if applicable)

5. **Percentage-Based Fees**
   - Consider percentage-based fees instead of fixed per-lot fees
   - Position size percentage-based calculation (if compliant)

---

## 10. References & Supporting Materials

### Internal Documents
- Trading Team Analysis: "Fee vs OVF islamic accounts.xlsx"
- Cost analysis and revenue modeling (TBD)

### Market Research
- Research Report: "Swap-Free Models in UAE for CFD Trading" (research-uae-swap-free-cfd-models.md)
- Competitive analysis: eToro, Equiti, Taurex, TMGM, ADSS, Alphaex Trade, Capital.com

### Regulatory References
- DFSA (Dubai Financial Services Authority) guidelines
- SCA (Securities and Commodities Authority) regulations
- Islamic finance principles (Sharia compliance)

### Competitive References
- eToro: https://www.etoro.com/trading/swap-free-account/
- Equiti: Swap-free account documentation
- TMGM: https://www.tmgm-maxtrade.com/en/swap-free-account
- Taurex: https://www.tradetaurex.com/swapfreeaccounts/

---

## Appendix A: Fee Calculation Examples

### Example 1: User in Bin 2
- **Position Size:** $15,000 total notional (Bin 2 range: $10,000 - $20,000)
- **Positions:** 2 lots
- **Bin 2 Fee:** $4.00 per lot per day
- **Daily Fee:** 2 lots × $4.00 = $8.00/day
- **Fee Calculation:** Based on position size (determines bin)
- **Fee Deducted From:** Equity (balance + unrealized P/L)
- **Note:** Fee applies daily after 7-day grace period

### Example 2: User Moving Between Bins
- **Day 1:** Position Size = $8,000 → Bin 1 → Fee: $2.00/lot/day
- **Day 5:** Position Size = $12,000 → Bin 2 → Fee: $4.00/lot/day (bin change)
- **Day 10:** Position Size = $25,000 → Bin 3 → Fee: $6.00/lot/day (bin change)
- **Positions:** 3 lots throughout (position size changes due to position value changes)
- **Note:** Fees adjust as position size changes and user moves between bins

### Example 3: Whitelisted User
- **User ID:** 12345 (whitelisted)
- **Position Size:** $50,000 (would be Bin 5)
- **Positions:** 5 lots
- **Fee Applied:** $0.00 (user is whitelisted)
- **Note:** Whitelist takes precedence over bin assignment

### Example 4: Fee Calculation and Payment
- **Position Size:** $12,000 total notional → Bin 2
- **Positions:** 2 lots
- **Fee Calculation:** 2 lots × $4.00/lot = $8.00/day (based on position size)
- **Account Balance:** $10,000
- **Unrealized P/L:** +$2,500
- **Total Equity:** $12,500 (balance + unrealized P/L)
- **Fee Deducted From:** $12,500 equity (not from $10,000 balance)
- **Note:** Fee is calculated based on position size, but paid from equity

---

**Document Status:** Proposal for stakeholder review and decision-making  
**Next Steps:** Address open questions, finalize fee levels, develop communication plan, technical assessment
