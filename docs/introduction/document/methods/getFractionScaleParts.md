Works the same as [RxCore.getFractionScaleString](./getFractionScaleString.md) except returns the numeric individual parts of the fraction string value.



### Syntax

```typescript
    RxCore.getFractionScaleString(decimalscale: number, fractionPrecision: number);
```

### Parameters
- `decimalscale`: **number** — The decimal scale value. 
- `fractionPrecision`: **number** — The precision of the fraction indicated by the denominator of a fraction.  Example : 1/16 = value 16


### Returns
- `fractionvalue`: **object** —  These are the fraction values for the decimal scale.

```typescript
    return {whole : number, numerator : number, denominator : number};
```

### Example

```typescript

      const drawingInchesForOneFoot = 12 / 0.25;
  
      const fraction = RXCore.getFractionScaleParts(drawingInchesForOneFoot, 64);
  
      const imperialNumerator = fraction.numerator;
      const imperialDenominator = fraction.denominator;

    //returns the fraction notation for 0.25 with a precision of 1/32 of an inch shouldl match to 3" = 1'.


```