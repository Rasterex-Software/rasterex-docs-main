Connection callback event that is called when the file and markup have finished loading.


```javascript
        function GUI_FileLoadComplete(){
              RxCore.GUI_FileLoadComplete.connect(function(fileurl, activefile){

                console.log(fileurl, "this file has completed loading")

              });
              
        
        }
```

### Callback Parameters
- **FileURL**: The file path of the loaded file or markup. Also returns "Compare" when a compare/overlay is loaded.