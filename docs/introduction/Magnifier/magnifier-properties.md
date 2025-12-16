---
title: Magnifier Properties
sidebar_label: Properties
sidebar_position: 4
---

## Overview

The `RxCore.magnifier` object exposes a set of properties that reflect the
current state of the magnifier and precision alignment system.

These properties are primarily used for inspection, synchronization with UI
state, and conditional logic in the host application.

---

## Magnifier Properties

### precisionMode

Indicates whether Precision Mode is currently active.

When `true`, the magnifier operates in precision alignment mode, enabling
snapping and anchor-based offset calculations.

**Type**

`boolean`

---

### magnificationScale

The current magnification scale factor used by the magnifier.

This value controls the zoom level applied to the magnified rendering.

**Type**

`number`

---

### anchor

The anchor point used during Precision Mode to calculate alignment offsets.

The anchor represents the reference point for snapping behavior.

**Type**

```ts
{ x: number; y: number }
```

---

### lastMousePos

Stores the last known pointer position used by the magnifier.

This value is used internally to update magnified rendering and overlay visuals
during interaction.

**Type**

```ts
{ x: number; y: number }
```
