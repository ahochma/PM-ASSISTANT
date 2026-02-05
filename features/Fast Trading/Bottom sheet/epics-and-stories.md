---
stepsCompleted: []
inputDocuments: [fast-order-component-product-solution.md, market-research-order-submission-ux.md]
---

# Fast Trading - Bottom Sheet Implementation Stories

## Overview

This document provides the story breakdown for implementing the bottom sheet component on top of the existing working app. The bottom sheet will be a reusable overlay component that can be triggered from TradeTable and InfoTab screens.

**Scope:** This focuses only on the bottom sheet container implementation, not the order entry form content.

---

## Story 1: Bottom Sheet Container for iOS

As a **mobile trader on iOS**,
I want **a bottom sheet to slide up smoothly when triggered from the app**,
So that **I can view content in an overlay without losing context of the current screen**.

**Acceptance Criteria:**

**Given** I am on any screen in the iOS app
**When** the bottom sheet is triggered (via API call or action)
**Then** a bottom sheet slides up from the bottom covering 60-80% of the screen
**And** the animation completes in 300-400ms with smooth 60fps performance
**And** the background is dimmed to 40-60% opacity
**And** the sheet has a draggable handle indicator at the top
**And** I can dismiss the sheet by swiping down or tapping the backdrop
**And** the sheet respects iOS safe areas and notch/status bar
**And** background content is non-interactive when sheet is open

**Technical Requirements:**
- Uses UISheetPresentationController (iOS 15+) or custom UIKit animation
- Supports iOS 15+ with proper safe area handling
- Respects iOS gesture recognizers and navigation stack
- Implements proper view hierarchy and z-index management
- Handles keyboard appearance/disappearance correctly

---

## Story 2: Bottom Sheet Container for Android

As a **mobile trader on Android**,
I want **a bottom sheet to slide up smoothly when triggered from the app**,
So that **I can view content in an overlay without losing context of the current screen**.

**Acceptance Criteria:**

**Given** I am on any screen in the Android app
**When** the bottom sheet is triggered (via API call or action)
**Then** a bottom sheet slides up from the bottom covering 60-80% of the screen
**And** the animation completes in 300-400ms with smooth 60fps performance
**And** the background is dimmed to 40-60% opacity
**And** the sheet has a draggable handle indicator at the top
**And** I can dismiss the sheet by swiping down or tapping the backdrop
**And** the sheet respects Android edge-to-edge display
**And** background content is non-interactive when sheet is open

**Technical Requirements:**
- Uses Material Design BottomSheet or custom CoordinatorLayout
- Supports Android API 24+ with proper edge-to-edge handling
- Respects Android back button and gesture navigation
- Implements proper view hierarchy and elevation
- Handles keyboard appearance/disappearance correctly

---

## Story 3: Swipe Gesture Handling and Dismissal

As a **mobile trader**,
I want **to dismiss the bottom sheet with a swipe-down gesture**,
So that **I can quickly close the overlay if I change my mind**.

**Acceptance Criteria:**

**Given** the bottom sheet is open on iOS or Android
**When** I swipe down on the sheet or handle
**Then** the sheet animates down and dismisses smoothly
**And** the gesture feels natural and responsive
**And** partial swipes show visual feedback (sheet follows finger movement)
**And** releasing before threshold cancels dismissal and returns sheet to open position
**And** velocity-based dismissal works (fast swipe dismisses even if not past threshold)
**And** haptic feedback is provided on dismissal

**Technical Requirements:**
- iOS: UIPanGestureRecognizer with velocity-based dismissal logic
- Android: SwipeDismissBehavior or custom gesture handling with velocity detection
- Both platforms: Proper gesture conflict resolution with scroll views inside sheet
- Both platforms: Haptic feedback on successful dismissal

---

## Story 4: Integration with TradeTable and InfoTab Entry Points

As a **mobile trader**,
I want **the bottom sheet to open from TradeTable and InfoTab screens**,
So that **I can access the bottom sheet functionality from existing app screens**.

**Acceptance Criteria:**

**Given** I am viewing the TradeTable screen
**When** I trigger the bottom sheet (via existing Buy/Sell action or new trigger)
**Then** the bottom sheet opens on top of the TradeTable
**And** the TradeTable remains visible (dimmed) behind the sheet
**And** the table scroll position is preserved when sheet dismisses

**Given** I am viewing the InfoTab screen
**When** I trigger the bottom sheet (via existing Buy/Sell action or new trigger)
**Then** the bottom sheet opens on top of the InfoTab
**And** the InfoTab content remains visible (dimmed) behind the sheet
**And** the InfoTab state is preserved when sheet dismisses

**Given** the bottom sheet is open from either entry point
**When** I dismiss the sheet
**Then** I return to the previous screen with all context preserved
**And** no navigation stack changes occur

**Technical Requirements:**
- iOS: Integration with existing TradeTable and InfoTab view controllers
- Android: Integration with existing TradeTable and InfoTab activities/fragments
- Both: Pass context/data to bottom sheet component via props/parameters
- Both: Maintain parent screen state during sheet lifecycle
- Both: Proper memory management and view lifecycle handling

---

**Document Status:** Ready for Development  
**Platforms:** iOS 15+, Android API 24+  
**Total Stories:** 4  
**Focus:** Bottom sheet container implementation only (overlay component)
