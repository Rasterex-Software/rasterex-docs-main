Use this method to search for 3D blocks that matches an array of search expression.
Typical use is with UI model tree nodes to swich 3D objects on/off.

### Syntax

```typescript
RxCore.search3DAttributesExArr(exprarr)
```

### Parameters

- `exprarr`: Array of **string** — Search expression or literal string using "?" and "*" wildcard characters.


### Returns

- **`Array<object>`** — Array of objects for each mesh that matches the search.
