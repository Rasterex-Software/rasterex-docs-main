Connection callback event that is called when the file and markup have finished loading.


### Callback Parameters
- `FileURL`: **string** - The file path of the loaded file or markup. Also returns "Compare" when a compare/overlay is loaded.
- `activefile`: **boolean** - Value is `true` if the loaded document is the currently active document.

### Example

```javascript

              RxCore.GUI_FileLoadComplete.connect(function(fileurl, activefile){

                  console.log(fileurl, " has completed loading");

              });


```

