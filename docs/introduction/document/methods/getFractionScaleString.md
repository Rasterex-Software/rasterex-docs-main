Use this method to get the fraction repsentation of a decimal scale value. These are typically fraction values used with Imperial measurement system. If a scale like 1:4 which has the decimal scale value of 0.25 is used the fraction value returned will be 3" = 1'.
This can be used in the UI to display the fractional scale value while still maintaning an internal decimal scale.


### Syntax

```typescript
    RxCore.getFractionScaleString(decimalscale: number, fractionPrecision: number);
```

### Parameters
- `decimalscale`: **number** — The decimal scale value. 
- `fractionPrecision`: **number** — The precision of the fraction indicated by the denominator of a fraction.  Example : 1/16 = value 16


### Returns
- `fractionvalue`: **string** — A string representation of the scale using fraction notation.

### Example

```typescript
var szfractionval = RxCore.getFractionScaleString(0.25, 32);
/
//returns the fraction notation for 0.25 with a precision of 1/32 of an inch shouldl match to 3" = 1'.


```