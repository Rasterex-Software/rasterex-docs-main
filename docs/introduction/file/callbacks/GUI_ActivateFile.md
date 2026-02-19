This callback notifies which file is currently active when using the client compare align feature.

### Callback Parameters
- `fileindex`: **number** - The index of the currently active file..


```javascript
    RxCore.GUI_ActivateFile(function(fileindex) {

        console.log("file now active " fileindex);

    });

```

