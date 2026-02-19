This callback is triggered when a print job is completed.

### Related methods
- [RXCore.print](../methods/print.md)
- [RXCore.printEx](../methods/printEx.md)
- [RXCore.printSizeEx](../methods/printSizeEx.md)


### Callback parameters

**None** - This callback does not return a value.

### Example:

```javascript
RxCore.onPrintComplete.connect(function () {

    console.log("print completed");

});
```
