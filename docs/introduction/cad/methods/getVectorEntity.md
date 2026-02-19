This method activates a tool that can be used to select a vector entity in a vector drawing, using the mouse. A callback event [RxCore.GUI_2DEntityInfo](../callbacks/GUI_2DEntityInfo.md) is triggered with a callback function to that returns information about the vector entity. This apply to vector geometry like lines, circles, arcs, polylines and other supported vector elements.

This can be used in combination with [RxCore.blockhoverevent](blockhoverevent.md))to enable mouse the return of vector information on mouse over. When this is used the information is returned using the [RxCore.GUI_2DEntityInfoScreen](../callbacks/GUI_2DEntityInfo.md) callback event.

### Syntax

```typescript
RxCore.getVectorEntity(onoff);
```

### Parameters
- `onoff`: **boolean** — Set to `true` to enable the tool, or `false` to disable it.

### Returns
- **NA** — This method does not return a value.