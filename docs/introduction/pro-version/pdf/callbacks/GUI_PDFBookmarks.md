This callback event returns the bookmarks from a PDF document when calling the RxCore.getPDFBookmarks() method.

### Callback Parameters
- **bookmarks**: An array of bookmark objects.


### Example:

```javascript



RxCore.GUI_PDFBookmarks.connect(function(bookmarks) {

    console.log("this PDF has ", bookmarks.length, " bookmarks" );
    
});
```