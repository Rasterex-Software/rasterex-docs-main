Callback that is called when a file upload is completed.

### Callback Parameters
- `openfile`: **string** - A string containing the file name of the file uploaded. 
  

### Example

  ```javascript
    RxCore.GUI_UploadComplete(function(openfile) {

        //if autoload on upload is off you can open the file here.

        RxCore.openFile(`${RxCore.Config.baseFileURL}${openfile}`);

    });

```

