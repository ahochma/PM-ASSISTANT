# UX Design: Swap-Free Administrative Fee Display

**Designer:** UX Designer (Sally)  
**Date:** January 2025  
**Context:** Swap-Free Charging Model v2 - Position Size-Based 5-Bin Model  
**Goal:** Simple, transparent fee display aligned with existing overnight funding UI pattern

---

## Design Principles

1. **Simplicity First** - Match the clarity of existing overnight funding display
2. **Transparency** - Clear, upfront disclosure (compliance requirement)
3. **Context-Aware** - Show applicable fee based on current position size and bin
4. **Consistency** - Align with existing UI patterns and terminology
5. **User Protection** - Highlight grace period protection clearly

---

## Current Pattern Analysis

### Existing Overnight Funding Display

```
Overnight funding - Buy
-0.0050%

Overnight funding - Sell
-0.0032%

Overnight funding time
12:00 AM
```

**Key Characteristics:**
- Simple label-value pairs
- Clean, minimal format
- Clear directional indicators (Buy/Sell)
- Time reference included
- Percentage-based values

---

## Proposed Design: Swap-Free Administrative Fee Display

### Design Approach: Simple Single-Line Display

Since swap-free fees are:
- Same for Buy and Sell (no directional difference)
- local currency amounts (not percentages)
- Based on position size bins (not time-based tiers)
- Have a 7-day grace period

**Recommended Format:** Simple, single-line display showing current fee rate

---

### Option 1: Minimal Display (Recommended)

**Standard Display (After Grace Period):**

```
Administrative fee (Swap-Free)
$4.00 per lot per day
```

**During Grace Period:**

```
Administrative fee (Swap-Free)
$0.00 per lot per day
(7-day grace period)
```

**Rationale:**
- Matches simplicity of current overnight funding display
- Shows dollar amount clearly
- Indicates "per lot per day" for clarity
- Grace period shown only when applicable
- No time reference needed (no time-based tiers)

---

### Option 2: Enhanced with Bin Information

**Standard Display:**

```
Administrative fee (Swap-Free)
$4.00 per lot per day
Bin 2 (Position size: $12,000 - $20,000)
```

**During Grace Period:**

```
Administrative fee (Swap-Free)
$0.00 per lot per day
(Grace period: Days 1-7)
```

**Rationale:**
- Provides more context about bin assignment
- Shows position size range for transparency
- Helps users understand fee structure
- Slightly more complex but more informative

---

### Option 3: Detailed with Expandable Info

**Standard Display:**

```
Administrative fee (Swap-Free)
$4.00 per lot per day
[ℹ️ View fee schedule]
```

**Expanded View (on click/hover):**

```
Administrative fee (Swap-Free)
$4.00 per lot per day

Fee Schedule (Bin 2):
Position size: $12,000 - $20,000
Fee: $4.00 per lot per day

Fee deducted from: Equity
[Close]
```

**Rationale:**
- Keeps main display simple
- Provides detailed information on demand
- Supports transparency requirements
- More flexible for future enhancements

---

## Recommended Design: Option 1 (Minimal Display)

### Rationale

1. **Matches Current Pattern** - Simple, clean format like overnight funding
2. **Essential Information Only** - Shows what user needs to know
3. **Compliance-Friendly** - Clear fee disclosure meets requirements
4. **User-Friendly** - No information overload
5. **Grace Period Clear** - Shows $0.00 with grace period note when applicable

---

## Display Rules & Logic

### Pre-Trade View (Before Opening Position)

**Display:**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
```

**Logic:**
- Show fee for estimated/projected position size bin
- If position size cannot be determined, show default or most common bin fee
- Optional: Show estimated bin based on position size input

### In-Position View (While Position is Open)

#### Scenario 1: Within Grace Period (Days 1-7)

**Display:**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(7-day grace period)
```

**Logic:**
- Calculate days since position opened
- If ≤ 7 days: Show $0.00 with grace period note
- Display days remaining (optional enhancement)

#### Scenario 2: After Grace Period (Day 8+)

**Display:**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
```

**Logic:**
- Determine current bin based on position size
- Display fee for current bin
- Update if bin changes (position size changes)

### Bin Change Scenario

**Display (when bin changes):**
```
Administrative fee (Swap-Free)
$6.00 per lot per day
(Updated: Bin 3)
```

**Logic:**
- Show current fee for new bin
- Optional: Brief indication that bin changed
- Update fee amount when position size moves to different bin

---

## Visual Specifications

### Text Formatting

**Label:**
- Format: "Administrative fee (Swap-Free)"
- Style: Standard label style (match overnight funding label)
- Font: Same as "Overnight funding" label

**Value:**
- Format: "$X.XX per lot per day"
- Style: Standard value style (match overnight funding value)
- Font: Same as overnight funding value
- Color: Standard text color (not negative/red, since it's an administrative fee)

**Grace Period Note:**
- Format: "(7-day grace period)" or "(Grace period: Days 1-7)"
- Style: Secondary text style
- Font: Smaller or lighter weight
- Color: Secondary text color

### Layout

**Structure:**
```
[Label]
[Value]
[Optional: Grace period note or bin info]
```

**Spacing:**
- Match spacing of overnight funding display
- Consistent vertical spacing between elements
- Align with existing UI grid system

---

## Edge Cases & Special Scenarios

### Whitelisted Users

**Display:**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(No fees - Whitelisted)
```

**Logic:**
- Check whitelist status
- If whitelisted: Show $0.00 with whitelist indicator
- No fee calculation needed

### Multiple Positions

**Display:**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
(Total position size: $15,000)
```

**Logic:**
- Calculate total position size across all positions
- Determine bin based on total position size
- Display single fee rate (same for all positions)
- Optional: Show total position size for context

### Position Size at Bin Boundary

**Display:**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
(Bin 2: $12,000 - $20,000)
```

**Logic:**
- If position size exactly equals bin threshold, use lower bin (or defined rule)
- Display current bin fee
- Optional: Show bin range for clarity

### Grace Period Counting

**Question:** How is grace period calculated?
- Per position (each position has its own 7-day grace period)?
- Per account (7-day grace period from first position)?
- **Decision Needed:** Grace period calculation rules

**Display Options:**

**Option A: Per Position Grace Period**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(Position opened: 3 days ago, 4 days remaining)
```

**Option B: Per Account Grace Period**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(Grace period ends: 4 days)
```

---

## Comparison: Overnight Funding vs. Swap-Free Admin Fee

### Overnight Funding (Standard Account)

```
Overnight funding - Buy
-0.0050%

Overnight funding - Sell
-0.0032%

Overnight funding time
12:00 AM
```

### Swap-Free Administrative Fee (New Design)

**During Grace Period:**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(7-day grace period)
```

**After Grace Period:**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
```

**Key Differences:**
- Single line (no Buy/Sell distinction)
- Dollar amount (not percentage)
- "Per lot per day" specification
- Grace period note when applicable
- No time reference (no time-based tiers)

---

## Implementation Considerations

### Data Requirements

**For Display:**
- Current position size (total notional value)
- Current bin assignment
- Grace period status (days since position opened, days remaining)
- Whitelist status (yes/no)
- Fee amount for current bin

**Calculations:**
- Position size calculation (total notional value of all open positions)
- Bin assignment (based on position size thresholds)
- Grace period calculation (days since position opened or account-level)
- Fee amount (bin fee × number of lots)

### Dynamic Updates

**Update Triggers:**
- Position opened/closed
- Position size changes (market movement)
- Bin changes (when position size moves to different bin)
- Grace period expiration (Day 8)
- Whitelist status changes

**Update Frequency:**
- Real-time or daily batch (based on bin assignment frequency)
- Display refresh when data changes

---

## Accessibility Requirements

1. **Screen Readers:**
   - Clear labels for all fee information
   - Descriptive text for grace period status
   - Bin information (if displayed) should be accessible

2. **Visual Clarity:**
   - Sufficient color contrast
   - Clear typography hierarchy
   - Readable font sizes

3. **Cognitive Load:**
   - Simple, clear format
   - No unnecessary complexity
   - Essential information only

---

## Mobile Considerations

### Simplified Mobile Display

**Standard:**
```
Admin fee (Swap-Free)
$4.00/lot/day
```

**With Grace Period:**
```
Admin fee (Swap-Free)
$0.00/lot/day
(Grace: 4 days left)
```

**Rationale:**
- Shorter labels for mobile space
- Essential information only
- Grace period shown concisely

---

## User Testing Considerations

### Key Questions to Validate

1. **Clarity:**
   - Do users understand the fee structure?
   - Is the "per lot per day" format clear?
   - Do users understand the grace period?

2. **Trust:**
   - Does the "Administrative fee" terminology feel fair?
   - Is transparency perceived as positive?
   - Do users trust the fee calculation?

3. **Compliance:**
   - Do users understand these aren't interest charges?
   - Is Sharia compliance communicated effectively?
   - Are regulatory requirements met?

---

## Recommended Implementation

### Primary Display (Recommended)

**Standard (After Grace Period):**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
```

**During Grace Period:**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(7-day grace period)
```

### Enhanced Version (Optional)

**With Bin Information:**
```
Administrative fee (Swap-Free)
$4.00 per lot per day
Bin 2
```

**With Grace Period Details:**
```
Administrative fee (Swap-Free)
$0.00 per lot per day
(Grace period: 4 days remaining)
```

---

## Design Specifications Summary

### Recommended Design: Option 1 (Minimal Display)

**Core Elements:**
- Label: "Administrative fee (Swap-Free)"
- Value: "$X.XX per lot per day"
- Grace period note: When applicable

**Key Features:**
- Simple, clean format matching current pattern
- Essential information only
- Grace period clearly communicated
- Consistent with existing UI patterns

**Compliance Alignment:**
- Uses "Administrative fee" terminology
- Clear fee disclosure
- Sharia-compliant framing

---

**Design Status:** Ready for stakeholder review and implementation  
**Priority:** High (required for v2 launch)  
**Complexity:** Low (simple implementation)
