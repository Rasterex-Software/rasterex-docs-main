Callback event that triggers when the 3D model is loaded, indicating that 3D search is now possible.

### Callback Parameters

- `URL`: **string**: The file URL of the loaded 3D model.
- `Active`: **boolean**: `true` 
if the file is active.

### Example

  ```javascript
    RxCore.GUI_search3Denabled(function(URL, Active) {

        if(Active){
            console.log("Search active for  ", URL);
        }
        

    });

```



