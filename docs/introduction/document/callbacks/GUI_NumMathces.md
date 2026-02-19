Connection callback that returns the number of matches for a text search.

### Related method
- [RxCore.textSearch](../methods/textSearch.md)

### Callback Parameters

- `nummatches`: **number**: The number of matches to a search expression.

### Example

```javascript


    RxCore.GUI_NumMathces.connect(function (nummatches) {
        console.log(nummatches, "matches found");

    });
```
