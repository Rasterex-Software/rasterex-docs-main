Sets the default export parameters that will be used with export methods that has no export parameters.

### Syntax

```typescript
    RxCore.setDefultExportparams(consolidate, format, UPI, paperSize, markupFlag);


```

### Parameters

- `consolidate`: **boolean** — Set to `true` to export only consolidated markup.
- `format`: **string** — Export format (e.g., `"PDF"`).
- `UPI`: **string** — Set to `"0"` (reserved for future use).
- `paperSize`: **string** — Paper size for export (e.g., `"A4"`).
- `markupFlag`: **number** — Export markup type: `0` for burned-in markup, `1` for native markup (PDF only).

### Returns

- **NA** — This method does not return a value.



  