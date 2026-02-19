Load a markup/annotation/measurement using a JSON string to the currently active Document.

### Syntax

```typescript
    RxCore.setMarkupfromJSON(JSONdata, DocObj);
```

### Parameters

- `JSONdata`: **string** — A string containing a markup object in JSON format.
- `DocObj`: **Document object** — The Document object where the annotation is to be added. If value is null the currently active document is used.

### Returns

- **NA** — This method does not return a value.