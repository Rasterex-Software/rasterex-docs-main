This callback returns a print job progress percentage while print a print job is active.

### Related methods
- [RXCore.print](../methods/print.md)
- [RXCore.printEx](../methods/printEx.md)
- [RXCore.printSizeEx](../methods/printSizeEx.md)


### Callback Parameters

- `pagenumtotal` **object**: an object with `current` and `total` number properties where `current` is the number for the currently printing page and `total` the total number of pages.


###Callback parameters **None**

### Example:

```javascript

RxCore.onPrintProgress.connect(function (pagenumtotal) {

    console.log("printed ", pagenumtotal.current, "of ", pagenumtotal.total);


});
```