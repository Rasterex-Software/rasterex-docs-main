Use this method to set the Scaling values for the currently active Document.
The structure of the scale object is determined by the host application and not RxCore.

### Syntax

```typescript
RxCore.updateScaleList(scalesOptions);
```

### Parameters

- `scalesOptions`: **array** — The array holds an object that is a set of scale and measurement values applied to measurement objects for the current document.

### Example
```typescript

scalesOptions = {
    dimPrecision : 2,
    imperialDenominator : 1,
    imperialNumerator : 1,
    isGlobal : true,
    isSelected : true,
    label : "1 Millimeter : 1 Millimeter",
    metric : "0",
    metricUnit : "Millimeter",
    pageRanges : Array[1, 2],
    preciseValue : 1,
    value : "1:1",
}

```

### Returns

- **NA** — This method does not return a value.