---
title: Viewer Layout and Initialization
sidebar_label: Viewer Layout
---

The layout object used with `RxCore.initialize()` defines how the viewer calculates its
rendering size within the host application.

It does **not** describe the structure of the application UI. Instead, it controls how the
viewer derives the size of its canvases from either the overall document or from explicit
dimensions.

---

## Layout Object Shape

```javascript
{
  offsetWidth: 0,
  offsetHeight: 0,
  absolute: false
}
```

---

## Meaning of the Layout Properties

### `offsetWidth` and `offsetHeight`

The interpretation of `offsetWidth` and `offsetHeight` depends on the value of the
`absolute` property.

---

### `absolute: false` (margin-based layout)

When `absolute` is set to `false`, `offsetWidth` and `offsetHeight` are treated as **margins
relative to the overall document**.

- `offsetWidth` reserves horizontal space (for example, a sidebar)
- `offsetHeight` reserves vertical space (for example, a header or toolbar)
- The viewer canvas size is calculated as:

> **document size minus the specified offsets**

This mode is intended for applications where the viewer shares space with other UI
components.

**Example: sidebar and header**

```javascript
RxCore.initialize({
  layout: {
    offsetWidth: 320,
    offsetHeight: 64,
    absolute: false
  }
});
```

In this example, the viewer renders in the remaining space after the sidebar and header
have been accounted for.

---

### `absolute: true` (dimension-based layout)

When `absolute` is set to `true`, `offsetWidth` and `offsetHeight` are treated as the
**explicit dimensions of the viewer canvases**.

- The viewer does not derive its size from the document
- No margin or remaining-space calculation is performed
- The canvas size is fixed to the specified width and height

This mode is intended for scenarios where the viewer must render at a specific size,
independent of the surrounding application layout.

**Example: fixed-size viewer**

```javascript
RxCore.initialize({
  layout: {
    offsetWidth: 1024,
    offsetHeight: 768,
    absolute: true
  }
});
```

---

## Layout Changes After Initialization

If the application layout changes after initialization (for example, when a sidebar opens,
closes, or resizes), update the viewer layout and trigger a resize so the canvases are
recalculated.

```javascript
RxCore.setLayout({
  offsetWidth: 320,
  offsetHeight: 64,
  absolute: false
});

RxCore.doResize();
```

---

## Multi-Instance Considerations

Each viewer instance manages its own layout configuration.

In applications with multiple viewer instances, each instance must be initialized and
updated with layout values that correspond to its allocated region in the host UI.

Layout values are not shared automatically between instances.

---

## Key Takeaway

> **The `absolute` flag controls whether layout values are interpreted as margins or as
> explicit canvas dimensions.**

- `absolute: false` → offsets are **margins relative to the document**
- `absolute: true` → offsets are **canvas dimensions**
