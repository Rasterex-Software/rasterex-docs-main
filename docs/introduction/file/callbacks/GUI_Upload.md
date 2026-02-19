Connection callback called when a file upload is in progress.

### Callback Parameters
- `upload`: **string** or **number**  - A string with values `"show"` or `"hide"` that can be used to hide or display the HTML element or an integer value indicating the progress of the upload.

### Example

  ```javascript
    RxCore.GUI_Upload(function(upload) {

        console.log("file uploaded " upload);

    });

```