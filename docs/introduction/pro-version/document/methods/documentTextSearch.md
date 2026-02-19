Use this method to initiate and perform text searches. Call `RxCore.clearDocumentTextSearch` to terminate text search. Search results are returned using the `RxCore.GUI_DocumentSearch` callback event.

### Version
(Pro version only)

### Syntax

```typescript
RxCore.documentTextSearch(text, casesense, wholeword)
```

### Parameters

- `text`: **string** — String to search for.
- `casesens`: **boolean** — Case sensitive. `true` for case-sensitive search, `false` for case-insensitive search.
- `wholeword`: **boolean** — Whole word flag. `true` = returns whole words only, `false` = finds part of word.



### Returns

- **NA** — This method does not return a value.