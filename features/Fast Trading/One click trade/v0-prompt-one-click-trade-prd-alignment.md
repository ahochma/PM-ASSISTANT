# v0 Prompt: One-Click Trading PRD Alignment

Use the prompt below in v0 to update your existing one-click trading prototype to match the updated PRD. Copy everything in the **Copy-paste block** section into v0.

---

## Copy-paste block (for v0)

Paste the following into v0. You can preface it with: "Update my existing one-click trading prototype with these changes:"

---

## Context
I have an existing prototype for **one-click trading** on mobile (market orders with minimal steps). The product requirements were updated. Please update the prototype to match the following.

## Phase 1 entry points only
- One-click trade is available **only from**: **Chart**, **Info tab**, and **Watchlist**.
- Remove or hide one-click from **TradeTable** and **Positions quick close** (they are out of scope for Phase 1).

## Two different UX patterns (important)

### Chart and Info tab — keep bottom sheet
- When the user taps Buy or Sell from the **chart** or the **instrument info tab**, keep the current flow: a **bottom sheet** opens.
- In the bottom sheet: user selects **number of contracts** (manual input and/or quick presets), then taps Buy or Sell to execute. No extra confirmation when one-click is enabled.
- Bottom sheet auto-dismisses after success (e.g. 2–3 seconds). Success message in/above the sheet.
- Do **not** change this flow for Chart and Info tab.

### Watchlist — new pattern: no bottom sheet, expandable row
- From the **Watchlist**, one-click must work **without** opening the bottom sheet.
- **Watchlist flow:**
  1. Each watchlist row can be **expanded** (e.g. tap/chevron to expand).
  2. When expanded, the row shows **on the watchlist screen itself**:
     - **Number of contracts** selector (manual input and/or quick presets, default to last used per instrument).
     - **Buy** and **Sell** buttons (or equivalent actions).
  3. User sets contract size **inline in the expanded row**, then taps **Buy** or **Sell** once to submit the order. That single tap is the "one click" (after size is set).
  4. No bottom sheet on Watchlist — contract size and Buy/Sell all live on the watchlist screen.
- Validation (e.g. insufficient balance) and errors should appear **inline** in the expanded row (not in a sheet).
- Success: show a **toast or inline confirmation** on the watchlist (e.g. "Order placed"); no sheet to dismiss.

## Summary of what to change
1. **Chart & Info tab:** Leave bottom sheet flow as-is (contract size in sheet, then Buy/Sell).
2. **Watchlist:** Replace any "open bottom sheet from watchlist" with **expandable watchlist rows** that show contract size + Buy/Sell inline; no bottom sheet from watchlist.
3. **Entry points:** Ensure one-click is only offered from Chart, Info tab, and Watchlist (not TradeTable or Positions in Phase 1).
4. **Opt-in:** Unchanged — user still opts in via settings and/or first-time prompt; same for Chart, Info tab, and Watchlist.

---

## How to use this with v0

1. Open your v0 project with the current one-click trading prototype.
2. Paste the prompt above (from "## Context" through "4. **Opt-in:** ...") into the v0 chat. Optionally start with: "Update my existing one-click trading prototype with these changes:" and then paste the block.
3. If v0 has multiple screens (Chart, Info tab, Watchlist), you can add: "Apply the Watchlist changes to the Watchlist screen only; leave Chart and Info tab flows as they are (bottom sheet)."
4. If the current prototype uses a bottom sheet for Watchlist as well, emphasize: "On Watchlist, remove the bottom sheet and use expandable rows with contract size and Buy/Sell on the watchlist screen instead."

## Optional: link to PRD

If v0 supports file or URL context, you can point it to the PRD for full detail:

- File: `_bmad-output/planning-artifacts/prd.md`
- Relevant sections: Executive Summary, MVP Entry Points (Phase 1 only), MVP Feature Set (Entry Points and Integration), and Functional Requirements FR-010, FR-010a, FR-010b, FR-011.
