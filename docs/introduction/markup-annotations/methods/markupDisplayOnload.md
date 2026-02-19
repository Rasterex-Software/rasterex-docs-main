This method is called before RxCore.initialize to enable all markup/annotations and measurements to be visilbe when a drawing loads.

This is used for collaboration and other cases where visiblitiy of markup/annotations and measurements on file load is necessary.

### Syntax

```typescript
RxCore.markupDisplayOnload(onoff)
```

### Parameters

- `onoff`: **boolean** — Set to `true` to turn visibility on, or `false` to turn it off.

### Returns

- **NA** — This method does not return a value.