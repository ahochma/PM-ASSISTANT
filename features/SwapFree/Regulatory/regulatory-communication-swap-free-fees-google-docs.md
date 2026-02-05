# Regulatory Communication: Swap-Free Administrative Fee System

**Document Type:** Regulatory Notification  
**Date:** January 2026  
**Version:** 1.0  
**Status:** For Regulatory Review

---

## 1. Executive Summary

This communication serves to notify the relevant regulatory authorities of our implementation of a **Swap-Free Administrative Fee System** for Islamic (swap-free) CFD trading accounts. This system introduces a compliant, position size-based administrative fee model designed to align with Islamic finance principles while ensuring full transparency and regulatory compliance.

**Key Points:**
- Fees are structured as **administrative/custody fees**, not interest-based charges
- Full compliance with Islamic finance principles (Sharia compliance)
- Transparent fee disclosure and user communication
- Position size-based fee structure with 7-day grace period
- Complete auditability and reporting capabilities

---

## 2. Regulatory Recipients

This communication is addressed to the following regulatory authorities:

1. **FSA** - Financial Services Authority
2. **FSCA** - Financial Sector Conduct Authority
3. **FCA** - Financial Conduct Authority
4. **ASIC** - Australian Securities and Investments Commission
5. **DFSA** - Dubai Financial Services Authority
6. **CySec** - Cyprus Securities and Exchange Commission
7. **SCA** - Securities and Commodities Authority (UAE)

---

## 3. Background and Rationale

### 3.1 Current State

Currently, swap-free (Islamic) account holders can hold leveraged CFD positions overnight without any charges, as traditional overnight funding fees (swaps) are prohibited under Islamic finance principles that forbid riba (interest). This results in:

- Full absorption of overnight funding costs by the platform
- No monetization mechanism for swap-free positions
- Revenue gap compared to standard accounts and market competitors

### 3.2 Market Context

Market research demonstrates that leading UAE CFD providers (eToro, Equiti, TMGM, Taurex) all implement administrative fee models for swap-free accounts that are:

- Accepted by regulators
- Compliant with Islamic finance principles
- Transparently disclosed to customers
- Based on administrative/custody fee structures (not interest)

### 3.3 Solution Approach

Our Swap-Free Administrative Fee System addresses this gap through:

- **Administrative fee structure** (not interest-based)
- **Position size-based pricing** (fair alignment with exposure)
- **7-day grace period** (market standard protection for short-term traders)
- **Full transparency** (clear disclosure and user communication)

---

## 4. Fee Model Description

### 4.1 Fee Structure

The system implements a **7-bin position size-based administrative fee model**:

| Feature | Description |
|---------|-------------|
| **Fee Type** | Administrative/custody fees (not interest-based) |
| **Calculation Basis** | Position size (total notional value of open positions) |
| **Grace Period** | 7 days (no fees charged during this period) |
| **Fee Application** | Daily fees deducted from equity (after grace period) |
| **Bin Structure** | 7 position size-based bins with dynamic reassignment |
| **Compliance Framing** | "Administrative/custody fee for maintaining open positions" |

### 4.2 Key Compliance Features

**Islamic Finance Compliance:**

- Fees are explicitly framed as **administrative or custody fees**, never as interest
- No reference to interest rates, funding rates, or swap rates
- Fees are based on position size (exposure), not time-based interest calculations
- Full alignment with Sharia principles prohibiting riba (interest)

**Transparency and Disclosure:**

- Clear upfront fee disclosure in trading interface
- Fee amount displayed before position opening
- All bin structures and fee levels transparently communicated
- Comprehensive FAQ and support documentation
- Terms and conditions explicitly state fee structure

**Fairness and Equity:**

- 7-day grace period protects short-term traders
- Position size-based pricing ensures fees align with exposure
- Dynamic bin reassignment reflects position size changes
- Whitelist capability for exceptional cases (optional)

---

## 5. Technical Implementation

### 5.1 Fee Calculation

- **Calculation Time:** Daily, synchronized with overnight funding calculation (OVF time)
- **Currency:** Fees calculated in USD with currency conversion rates saved at calculation time
- **Basis:** Position size (total notional value) determines bin assignment
- **Deduction:** Fees deducted from equity (balance + unrealized profit/loss)

### 5.2 Grace Period

- **Duration:** 7 days per position
- **Application:** No fees charged during grace period
- **Tracking:** Grace period tracked per position, not per account

### 5.3 Bin Assignment

- **Structure:** 7 bins based on position size thresholds
- **Reassignment:** Dynamic bin reassignment on daily calculation
- **Transparency:** Current bin and fee level visible to users

### 5.4 Audit and Reporting

- Complete audit logging (similar to Dynamic Overnight Fee Calculator)
- Fee calculation history
- Bin assignment history
- Revenue reporting
- Management statistics
- Full traceability for regulatory review

---

## 6. User Communication and Disclosure

### 6.1 Pre-Trade Disclosure

- Estimated administrative fee displayed before position opening
- Clear indication of 7-day grace period (0$ for first 7 days)
- Tooltip showing all bin details and fee structure
- Fee marked as "Administrative fee (Swap-Free)" - never as interest

### 6.2 Ongoing Disclosure

- Real-time fee impact visibility
- Current bin assignment displayed
- Fee deduction clearly shown in account statements
- Closed positions screen includes fee representation

### 6.3 Documentation

- Comprehensive FAQ addressing Islamic account compliance
- Terms and conditions explicitly describing fee structure
- Support team training on fee explanation
- Clear communication that fees are administrative, not interest-based

---

## 7. Regulatory Compliance Assurance

### 7.1 Islamic Finance Principles

✓ **No Interest (Riba):** Fees are administrative/custody fees, not interest  
✓ **Transparency:** Full disclosure of all fees and fee structures  
✓ **Fairness:** Position size-based pricing aligns with exposure  
✓ **Sharia Compliance:** Structure reviewed for compliance with Islamic finance principles

### 7.2 Regulatory Requirements

✓ **Transparent Disclosure:** All fees clearly disclosed before and during trading  
✓ **Auditability:** Complete audit trails and reporting capabilities  
✓ **User Protection:** 7-day grace period protects short-term traders  
✓ **Fair Treatment:** Position size-based structure ensures equitable pricing

### 7.3 Market Alignment

✓ **Industry Standard:** Aligned with market leaders (eToro, Equiti, TMGM, Taurex)  
✓ **Competitive Positioning:** Grace period and fee structure competitive with market  
✓ **Accepted Practice:** Administrative fee models are standard and accepted in UAE market

---

## 8. Implementation Timeline

**Phase 1: Communication (30-60 days before launch)**

- Advance notice to existing customers
- Clear explanation of fees, rationale, and compliance
- FAQ and support resources deployment

**Phase 2: Launch**

- Full system implementation
- Ongoing monitoring and adjustment
- Continuous compliance review

**Phase 3: Post-Launch**

- Regular reporting and audit
- User feedback monitoring
- Compliance verification

---

## 9. Monitoring and Reporting

We commit to:

- **Regular Compliance Review:** Ongoing verification of fee structure compliance
- **User Feedback Monitoring:** Tracking customer inquiries and concerns
- **Audit Trail Maintenance:** Complete records available for regulatory review
- **Performance Metrics:** Monitoring churn, revenue, and user satisfaction
- **Regulatory Reporting:** Available upon request

---

## 10. Contact Information

For questions, clarifications, or regulatory review requests, please contact:

**Compliance Team:** [To be filled]  
**Product Team:** Amit Hochma  
**Legal Team:** [To be filled]

---

## 11. Supporting Documentation

The following documents are available for regulatory review:

1. **Product Requirements Document (PRD)** - Complete technical and functional specifications
2. **Product Concept Document** - Market research and competitive analysis
3. **User Interface Design** - Fee disclosure and transparency measures
4. **FAQ Documentation** - Customer communication materials
5. **Terms and Conditions** - Legal framework and user agreements

---

## 12. Conclusion

The Swap-Free Administrative Fee System represents a compliant, transparent, and fair approach to monetizing swap-free accounts while maintaining full alignment with:

- Islamic finance principles (Sharia compliance)
- Regulatory requirements for transparency and disclosure
- Market standards and competitive positioning
- User protection and fairness principles

We are committed to maintaining the highest standards of compliance and transparency, and we welcome any questions or feedback from regulatory authorities.

---

**Document Status:** Submitted for Regulatory Review  
**Next Steps:** Awaiting regulatory feedback and approval

---

*This document is confidential and intended solely for regulatory review purposes.*
