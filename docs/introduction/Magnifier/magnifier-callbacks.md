---
title: Magnifier Callbacks
sidebar_label: Callbacks
sidebar_position: 5
---

## Overview

RxCore exposes GUI callbacks that notify the host application about
magnifier-related events such as activation, alignment point selection,
and completion of alignment operations.

Callbacks originate from internal RxCore GUI event objects and are exposed
to integrators through a `.connect(fn)` mechanism. The examples shown below
demonstrate **one possible implementation pattern** for connecting handlers;
they are not the callbacks themselves.


## Callback connection model

Internally, magnifier-related events are implemented as GUI event objects
(for example `RxCore.GUI_Magnify`) that expose a `.connect(callback)` method.

Connecting a callback binds your function so it is executed when the
corresponding event is triggered inside RxCore.

## Callbacks

### RxCore.GUI_Magnify

Notifies the host application that the magnifier should be activated or
deactivated.

**Callback signature**

```ts
(active: boolean) => void
```

**Parameters**

- `active` – `true` if the magnifier should be activated, `false` otherwise

---

### RxCore.GUI_AlignPoint

Notifies the host application that an alignment point has been selected.

**Callback signature**

```ts
(pointIndex: number) => void
```

**Parameters**

- `pointIndex` – Identifier of the selected alignment point

---

### RxCore.GUI_AlignPointComplete

Notifies the host application that the current alignment point operation
has completed.

**Callback signature**

```ts
() => void
```

**Parameters**

None

---

## Example implementation pattern


```ts
RxCore.GUI_Magnify.connect(callback);
RxCore.GUI_AlignPoint.connect(callback);
RxCore.GUI_AlignPointComplete.connect(callback);
```

The following examples illustrate a common way to register magnifier callbacks
in a viewer or host application.


```ts

onGuiMagnify(active: boolean){
  // show or hide magnifier UI
};

RxCore.GUI_Magnify.connect(onGuiMagnify);


onGuiAlignPoint(pointIndex: number){
  // activate magnifier for selected alignment point
};

RxCore.GUI_AlignPoint.connect(onGuiAlignPoint);

onGuiAlignPointComplete(){
  // finalize alignment and clean up UI
};

RxCore.GUI_AlignPointComplete.connect(onGuiAlignPointComplete);

```


---

## Magnifier events

The magnifier instance also exposes events that fire when Precision Mode
is entered or exited. These callbacks are assigned directly on the
`RxCore.magnifier` object.

## Precision Mode events
There are two events that notify when precision mode specifically for alignment purposes is turned on and off.

### RxCore.magnifier.onEnterPrecision

Triggered when Precision Mode is entered.

```ts
    (anchor: { x: number; y: number }) => void
```
### RxCore.magnifier.onExitPrecision

Triggered when Precision Mode is exited.

```ts
    () => void
```

## Magnifier events implementation examples.

```ts
  notifyEnterPrecision(anchor: { x: number; y: number }) {
    if (this.onEnterPrecision) {
      this.onEnterPrecision(anchor);  // Trigger the callback for precision mode entry
    }
  }

  // Notify that precision mode has been exited
  notifyExitPrecision() {
    if (this.onExitPrecision) {
      this.onExitPrecision();  // Trigger the callback for precision mode exit
    }
  }
```
