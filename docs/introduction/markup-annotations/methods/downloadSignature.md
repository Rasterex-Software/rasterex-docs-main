Downloads a signature image file from server.

### Syntax

```typescript
RxCore.downloadSignature(username, binitial)
```

### Parameters

- `username`: **string** — Unique user name that indentifies a signature image previously uploaded using uploadSignature.
- `binitial`: **boolean** — Set to `true` to download initial image instead of full signature.



### Returns

- **NA** — This method does not return a value.

### Associated callback 

- RxCore_GUI_getsignatureComplete - used to handle the returned signature image.

