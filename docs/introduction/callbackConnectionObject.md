---
title: Callback Connection Method
sidebar_label: Callback Connection
---

RxCore callback events are exposed as **signal objects**.  
To receive events, the host application must connect a callback function using
the `.connect(callback)` method.

Direct assignment of callback functions is **not supported**.

Signal objects manage one or more subscribers internally.Assigning a function directly replaces the signal reference, preventing the internal dispatch mechanism from delivering events.

---

## How It Works

1. Define a JavaScript function that will act as the callback handler.
2. Use the `connect` method on the RxCore callback **signal object**.
3. Callbacks should be connected before the event is expected to fire.

---

## Example

```javascript
RxCore.GUI_MarkupLayers.connect(function (markuplayers) {
  // Handle updated markup layer information
});
```

:::warning Not supported
Direct assignment of a function to a signal object will not trigger callbacks.

```javascript
// ❌ This will not work
RxCore.GUI_MarkupLayers = function () {
  // This function will never be called
};

```