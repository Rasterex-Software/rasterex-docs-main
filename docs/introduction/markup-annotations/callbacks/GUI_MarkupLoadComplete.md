Connection callback that is called when markup is loaded.

### Callback Parameters
- **Nummarkupfiles**: Number of markup files loaded.
- **fileindex**: Index of the file that has the markup
- **activefile** : true if the file is the active file.

### Example

```javascript
RxCore.GUI_MarkupLoadComplete.connect(function (Nummarkupfiles, fileindex, activefile) {

    console.log("The file with index ", fileindex, "has loaded markup from ",  Nummarkupfiles, " files");
   
  
});
```

