Returns a JSON structure containing current markup elements for the active file.
The JSON structure is returned using the [GUI_MarkuplistJSON](../callbacks/GUI_MarkuplistJSON) callback event.

### Syntax

```typescript
    RxCore.markupGetJSON(unselect)
```

### Parameters

- `unselect`: **boolean** — Set to `true` it will unselect all currently selected markup/annotations before returning data, or `false` to allow selected markup/annotations to remain selected.

### Returns

- **NA** — This method does not return a value.