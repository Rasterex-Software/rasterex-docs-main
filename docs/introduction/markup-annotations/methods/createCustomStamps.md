A method to create custom stamps using images.

### Associated callback events

- [RxCore.GUI_CustomStamps](../callbacks/GUI_CustomStamps.md)

### Syntax

```typescript
    RxCore.createCustomStamps(StampInfo);
```
### Parameters

- `StampInfo`: **object**: An object that holds information on the created stamp and type of event.

```javascript
stampdata.type: // Type of event with values
    2: // stampdata.data = library name
    3: // stampdata.data = number of stamps
    5: // stampdata.data = stamp image object
stampdata.index = stamp name;
stampdata.width = stamp width;
stampdata.height = stamp height;
```

### Returns

- **NA** — This method does not return a value.
