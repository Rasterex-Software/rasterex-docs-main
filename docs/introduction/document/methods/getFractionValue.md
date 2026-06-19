Use this method to get the fraction repsentation of a decimal length value. These are typically fraction values used with Imperial measurement system. This can be used when calculting scaling for a drawing during calibration.


### Syntax

```typescript
    RxCore.getFractionValue(decimalLength, fractionPrecision);
```

### Parameters
- `decimalLength`: **number** — The decimal length value. 
- `fractionPrecision`: **number** — The precision of the fraction indicated by the denominator of a fraction.  Example : 1/16 = value 16


### Returns
- `fractionvalue`: **string** — A string representation of the length using fraction notation.

### Example

```typescript
var szfractionval = RxCore.getFractionValue(110.5, 32);
//returns the fraction notation for 110.5 with a precision of 1/32 of an inch.


```