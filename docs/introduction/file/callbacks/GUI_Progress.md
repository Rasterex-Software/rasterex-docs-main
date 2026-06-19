Connection callback called when a file load is in progress.

### Callback Parameters
- `progress`: **number** - The percent of the file loaded.

### Example

  ```javascript
    RxCore.GUI_Progress(function(progress) {

        console.log(progress " % of file has loaded");

    });

```



