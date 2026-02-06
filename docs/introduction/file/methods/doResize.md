Notifies `rxcorefunctions` about a change in the size of the canvas.

### Syntax

```typescript
RxCore.doResize();
//optionally 
RxCore.doResize(offsetWidth, offsetHeight);

```

### Parameters

RxCore.doResize can be called without parameters. If not provided the current layout values set with RxCore.setLayout is used.

- `offsetWidth`: **number** — New width in pixels to adjust the canvas. 
- `offsetHeight`: **number** — New height in pixels to adjust the canvas.

### Returns

- **NA** — This method does not return a value.