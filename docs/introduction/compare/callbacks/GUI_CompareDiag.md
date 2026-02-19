Connection object used to specify an HTML element for selecting and creating a compare overlay.

### Callback Parameters
- `OpenFileNames`: **Array** - Array of file names for files currently open in RxView360 that can be used in a Compare overlay.

### Example

```typescript

RxCore.GUI_CompareDiag.connect(function(OpenFileNames){

    console.log("open files ", OpenFileNames);

});

```