---
title: Magnifier Methods
sidebar_label: Methods
sidebar_position: 3
---

## Overview

The `RxCore.magnifier` object exposes methods used to configure magnified
rendering, control magnification scale, and manage Precision Mode behavior.
All methods are accessed through the `RxCore.magnifier` instance.

---

## Magnifier Methods

### setCanvas

Assigns the canvases used by the magnifier.

**Syntax**

```ts
RxCore.magnifier.setCanvas(
  baseCanvas: HTMLCanvasElement,
  overlayCanvas: HTMLCanvasElement,
  snapCanvas: HTMLCanvasElement
)
```

**Parameters**

- `baseCanvas` – Canvas used for rendering magnified document content
- `overlayCanvas` – Canvas used for crosshairs and visual guides
- `snapCanvas` – Canvas used for snap indicators during alignment

**Returns**

None

---

### setContext

Sets the rendering context and dimensions for the magnifier canvas.

**Syntax**

```ts
RxCore.magnifier.setContext(
  ctx: CanvasRenderingContext2D,
  width: number,
  height: number
)
```

**Parameters**

- `ctx` – Rendering context
- `width` – Canvas width
- `height` – Canvas height

**Returns**

None

---

### setOverlayContext

Sets the rendering context for the overlay canvas.

**Syntax**

```ts
RxCore.magnifier.setOverlayContext(ctx)
```

**Parameters**

- `ctx` – Overlay rendering context

**Returns**

None

---

### setSnapContext

Sets the rendering context for the snap canvas.

**Syntax**

```ts
RxCore.magnifier.setSnapContext(ctx)
```

**Parameters**

- `ctx` – Snap rendering context

**Returns**

None

---

### resetContext

Resets internal scaling and transformations applied to the magnifier.

**Syntax**

```ts
RxCore.magnifier.resetContext()
```

**Returns**

None

---

### setScale

Sets the magnification scale directly.

**Syntax**

```ts
RxCore.magnifier.setScale(nscale)
```

**Parameters**

- `nscale` – Magnification factor

**Returns**

None

---

### stepScale

Adjusts the magnification scale in fixed increments.

**Syntax**

```ts
RxCore.magnifier.stepScale(bUp)
```

**Parameters**

- `bUp` – Increase scale if `true`, decrease if `false`

**Returns**

None

---

### setActive

Enables or disables magnifier rendering.

**Syntax**

```ts
RxCore.magnifier.setActive(active)
```

**Parameters**

- `active` – Enable or disable magnifier

**Returns**

None

---

### update

Updates magnifier position, snapping behavior, and overlay visuals.

**Syntax**

```ts
RxCore.magnifier.update({ x, y })
```

**Parameters**

- `x` – Pointer X coordinate
- `y` – Pointer Y coordinate

**Returns**

None

---

### enterPrecisionMode

Enters Precision Mode and sets the anchor point used for alignment.

**Syntax**

```ts
RxCore.magnifier.enterPrecisionMode(anchor)
```

**Parameters**

- `anchor` – Anchor identifier

**Returns**

None

---

### exitPrecisionMode

Exits Precision Mode and restores normal magnifier behavior.

**Syntax**

```ts
RxCore.magnifier.exitPrecisionMode()
```

**Returns**

None

---

### suspend

Temporarily suspends magnifier updates and rendering.

**Syntax**

```ts
RxCore.magnifier.suspend(state)
```

**Parameters**

- `state` – Suspend state

**Returns**

None

---

### clearOverlay

Clears all overlay visuals.

**Syntax**

```ts
RxCore.magnifier.clearOverlay()
```

**Returns**

None

---

### drawOverlayPoint

Draws an overlay point or crosshair.

**Syntax**

```ts
RxCore.magnifier.drawOverlayPoint(x, y, color?, size?)
```

**Parameters**

- `x` – X coordinate
- `y` – Y coordinate
- `color` – Optional color
- `size` – Optional size

**Returns**

None

---

### drawCrosshair

Draws a crosshair at the current magnifier position.

**Syntax**

```ts
RxCore.magnifier.drawCrosshair(color?, size?, box?)
```

**Parameters**

- `color` – Optional color
- `size` – Optional size
- `box` – Draw bounding box if `true`

**Returns**

None

