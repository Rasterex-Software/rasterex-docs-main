Connection callback event that is called when PDF page dimension data has been extracted during file load.

### Callback Parameters

- **FileURL**: The file path of the loaded file.
- **bActiveFile**: Boolean indicating if the file is the currently active file.


### Example

```javascript
    RxCore.GUI_pagedimLoadComplete.connect(function (FileURL, bActiveFile){

        console.log("page dimensions are set for ", FileURL);

    });

```