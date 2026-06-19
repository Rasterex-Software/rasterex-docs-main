This callback indicates the earliest possible time to enable pen table settings when a CAD file that support pen tables is loaded.


### Callback Parameters
- **none**: This callback does not return any values.


### Example of implementation.

```javascript

        function GUI_autopenTable(){

            RxCore.GUI_autopenTable.connect(onAutoPenTable);

            function onAutoPenTable(){
                console.log("use of pen table is ready");
            }
        }


```

