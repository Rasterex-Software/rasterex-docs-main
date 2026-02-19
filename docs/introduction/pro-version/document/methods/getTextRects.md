This method searches for a text in a PDF document, finds all instances of the text and return a set of rectangles indicating the position and size of the search text. The rectangles are returned using the `GUI_NumMatchesRect` callback.

### Version
(Pro version only)

### Related metods.
- [endGetTextRects](endGetTextRects.md)

### Related callbacks.
- [GUI_NumMatchesRect](../callbacks/GUI_NumMathcesRect.md)

Terminates the operation started with `getTextRects` and resets values.

### Syntax

```typescript
RxCore.getTextRects()
// Terminates operation started with RxCore.getTextRects
```

### Parameters

- **None**

### Returns

- **NA** — This method does not return a value.