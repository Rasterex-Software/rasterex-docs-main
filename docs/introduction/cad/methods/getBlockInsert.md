This method activates a tool that can be used to select a vector block in a vector drawing, using the mouse. A callback event [RxCore.GUI_2DBlock](../callbacks/GUI_2DBlock.md) is triggered and returns information about the block.

This can be used in combination with [RxCore.blockhoverevent](blockhoverevent))to enable the return of vector information on mouse over. When this is used the information is returned using the [RxCore.GUI_2DBlockHover](../callbacks/GUI_2DBlockHover.md) callback event.

### Syntax

```typescript
RxCore.getBlockInsert(onoff);
```

### Parameters
- `onoff`: **boolean** — Set to `true` to enable the tool, or `false` to disable it.

### Returns
- **NA** — This method does not return a value.