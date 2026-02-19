This is used during a collaboration session to make sure that the user not currently having the control does not have access to update the current page view. This affects the default scroll wheel handling, RxCore.zoomFit, RxCore.zoomHeight, RxCore.zoomWidth, RxCore.zoomIn, RxCore.zoomOut, RxCore.setMonoChrome, RxCore.toggleBackground, RxCore.getPageRotation, RxCore.rotateClockwise, RxCore.rotatePage, RxCore.rotate and RxCore.zoomWindow.

### Syntax

```typescript
RxCore.setCollabBlock(onoff);
```

### Parameters

- `onoff`: **boolean** — toggles the blocking on and off.


### Returns

- **NA** — This method does not return a value.

