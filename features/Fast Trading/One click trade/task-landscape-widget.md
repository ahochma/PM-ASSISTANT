1. Background 
One-click trading from the chart enables seamless market order execution directly from the full-screen chart context. In landscape mode, vertical space is highly constrained, making the standard bottom sheet interaction unusable as it would obscure the chart analysis area.

Problem Statement 
Traders using landscape mode for deep technical analysis cannot execute orders without losing context (either by rotating the screen or opening a full-screen sheet), which causes friction and missed opportunities.

Goal 
Provide a compact "On-Chart Execution Widget" for landscape mode that allows instant execution while maintaining 100% chart visibility.

Scope 
- **Widget UI:** Implement a semi-transparent, compact panel docked to the side (default right) of the chart.
- **Elements:**
  - Contract Size Input (Percentage Chips + Manual).
  - Buy / Sell Action Buttons (Stacked or Side-by-Side).
  - Real-time Price Display within buttons.
- **One-Click Logic:** Instant execution of market orders when enabled.
- **Opt-In Flow:** Trigger a centered Modal prompt on first use (if disabled).
- **Feedback:** Subtle toast notification near the widget upon execution.

UX / Behavior Requirements 
- **Positioning:** Floating overlay, anchored to the right safe area (notch aware).
- **Visibility:** Always visible when user has One-Click enabled? (Refinement: Persistent but minimizable).
- **Interactions:** 
  - Tapping "25%" updates size instantly.
  - Tapping Buy/Sell sends order immediately.
  - Success message appears as a non-blocking toast.
- **Opt-In:** If user clicks Buy/Sell and One-Click is DISABLED -> Show centered Modal "Enable One-Click?".

Out of Scope 
- Draggable widget (fixed position for MVP).
- Advanced order types (Limit/Stop) in this widget.

Acceptance Criteria 
- Widget appears correctly only in Landscape orientation.
- Chart is fully interactive behind the widget.
- Tapping Buy/Sell executes order immediately (if enabled).
- Opt-In Modal appears correctly on first attempt (if disabled).
- Real-time prices update within the buttons.
- No screen rotation required at any point.

QA Plan:
Feature flag: `IsLandscapeOneClickWidgetEnabled`
- Verify when ff disabled: Widget is hidden; standard behavior applies.
- When ff enabled: Widget appears in landscape charts. Verify opt-in flow and instant execution.

Heap Events Requirements:
Event 1: `landscape_widget_interaction`
When to fire:
User interacts with the widget (size change or click).
Event properties:
`screen_name`: "chart_landscape"
`action`: "size_change" | "buy_click" | "sell_click"
`one_click_enabled`: true/false

Event 2: `landscape_opt_in_view`
When to fire:
User sees the opt-in modal in landscape.
Event properties:
`source`: "landscape_widget"
