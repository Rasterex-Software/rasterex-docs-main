Use this method to get the current measurement system used for measurement.

### Syntax

```typescript
RxCore.getUnit()
```

### Parameters

- **NA** — This method does not have any parameters.

### Returns

- `unitobj`: **object** — An Object with various measurement values.

```typescript


            var unitobj = {
                unit : Unitofmeasure, //integer - `1` = Metric, `2` = Imperial, `3` = System, `4` = 
                unitname : uname, // String -  Metric, Imperial, System or Custom
                subunit : SubmeasureUnit, // String -  mm, cm, dm etc.
                label : Unitlabel, // String mm, Inch
                Arealabel : AreaUnitlabel // String "mm\u00B2"
            };
```
