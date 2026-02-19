Use this method to select a 2D vector block in a vector drawing by using the Block ID. A callback event [RxCore.GUI_2DBlock](../callbacks/GUI_2DBlock.md) is triggered and returns information about the block.

### Syntax

```typescript
RxCore.selectVectorBlockInsert(blockid, bSelected);
```

### Parameters

- `blockid`: **number** — Block ID of the 2D vector block to select.
- `bSelected`: **boolean** — Set to `true` to select and `false`to deselect.


### Returns

- **NA** — This method does not return a value.