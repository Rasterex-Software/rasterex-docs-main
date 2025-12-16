---
title: Magnifier Alignment Process
sidebar_label: Alignment Process
sidebar_position: 6
---

## Overview

The Magnifier Alignment Process describes how the Magnifier, RxCore GUI callbacks,
and Magnifier object events work together to support high‑precision alignment
workflows, such as overlay or compare alignment.

This section focuses on **runtime behavior and interaction flow**. All methods,
properties, and callbacks referenced here are documented in their respective
API sections and are not redefined.

---

## Actors and Responsibilities

The alignment process involves three cooperating parts:

- **RxCore**
  - Emits GUI callbacks related to alignment workflow
  - Maintains alignment state and triggers Precision Mode transitions

- **Magnifier object**
  - Manages magnification state and precision alignment behavior
  - Emits events when Precision Mode is entered or exited

- **Host application / viewer**
  - Connects callbacks and events
  - Manages UI and user interaction
  - Forwards pointer updates to the magnifier

---

## High‑level Workflow

At a high level, the alignment process follows these steps:

1. Alignment mode is initiated in the host application
2. RxCore signals that the magnifier should be activated
3. An alignment point is selected
4. Precision Mode is entered
5. User performs fine‑grained alignment using the magnifier
6. Alignment point operation completes
7. Precision Mode is exited and magnifier is deactivated

Each step is described in more detail below.

---

## Step 1: Alignment initiation

The alignment process typically begins when the host application enters an
alignment or compare mode.

At this stage:
- Callback connections are already registered
- The magnifier is inactive
- Precision Mode is disabled

No magnifier rendering occurs yet.

---

## Step 2: Magnifier activation

RxCore notifies the host application that the magnifier should be activated
by emitting the following GUI callback:

- `RxCore.GUI_Magnify`

The host application typically responds by:
- Creating or showing the magnifier UI
- Calling `RxCore.magnifier.setActive(true)`
- Initializing or validating magnifier canvases and contexts

---

## Step 3: Alignment point selection

When the user selects an alignment point, RxCore emits:

- `RxCore.GUI_AlignPoint`

This callback indicates which alignment point is active. The host application
may use this information to:
- Position the magnifier
- Prepare Precision Mode entry
- Update visual indicators

At this stage, the magnifier may already be visible but Precision Mode
is not yet active.

---

## Step 4: Entering Precision Mode

When fine‑grained alignment begins, the host application enables Precision Mode
by calling:

- `RxCore.magnifier.enterPrecisionMode(anchor)`

As a result:
- The magnifier switches to precision alignment behavior
- The magnifier emits the `onEnterPrecision` event
- Snapping and anchor‑based offset calculations become active

The `anchor` parameter defines the reference point used during alignment.

---

## Step 5: Interactive alignment

While Precision Mode is active:

- Pointer or mouse movement is forwarded to the magnifier using:
  - `RxCore.magnifier.update({ x, y })`
- The magnifier updates:
  - Magnified rendering
  - Overlay visuals (crosshairs, guides)
  - Snap behavior

This step continues until the user completes alignment for the selected point.

---

## Step 6: Alignment point completion

When the alignment operation for the current point finishes, RxCore emits:

- `RxCore.GUI_AlignPointComplete`

The host application typically responds by:
- Finalizing alignment state
- Optionally suspending or hiding the magnifier UI
- Preparing for the next alignment point, if any

---

## Step 7: Exiting Precision Mode

When Precision Mode is no longer required, the host application calls:

- `RxCore.magnifier.exitPrecisionMode()`

As a result:
- Precision alignment behavior is disabled
- The magnifier emits the `onExitPrecision` event
- Normal magnifier behavior is restored

The magnifier may remain active or be deactivated depending on workflow.

---

## Step 8: Magnifier deactivation

Once alignment is complete, RxCore may emit:

- `RxCore.GUI_Magnify` with `active = false`

The host application typically responds by:
- Calling `RxCore.magnifier.setActive(false)`
- Hiding or destroying the magnifier UI
- Resetting related UI state

---

## Notes and Considerations

- The alignment process is **event‑driven**; RxCore emits GUI callbacks while
  the host application controls magnifier behavior explicitly.
- Precision Mode is a **Magnifier concern**, not a GUI callback.
- UI rendering and input handling are intentionally outside RxCore and
  must be implemented by the host application.
- The exact sequence of UI actions may vary, but the callback and event
  ordering remains consistent.

