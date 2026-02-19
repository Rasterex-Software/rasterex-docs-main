Callback event that is called when markup load is complete.

### Callback Parameters
- `Nummarkupfiles`: **number** - Number of markup files loaded.
- `fileindex`: **number** - Index of the file that has the markup.
- `activefile`: **boolean** - true if the file is the active file.

### Example

```javascript
    RxCore.GUI_MarkupLoadComplete.connect(function (Nummarkupfiles, fileindex, activefile) {

        console.log("The file with index ", fileindex, "has loaded markup from ",  Nummarkupfiles, " files");
    
    
    });
```

