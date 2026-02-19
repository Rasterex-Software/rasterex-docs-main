This is a connection callback object that returns one or more vector block IDs when the `RxCore.pickPolygon()` tool is used.


### Callback Parameters
- `blocks`: **object** or **array of object** — If multi selection is on the return will be an array of vector block IDs or Rasterex Space objects If multi selection is off this is a single block ID or Rasterex Space object.


#### Example
```javascript

RxCore.GUI_2DBlock.connect(function(blocks){

    if (blocks) {
        console.log(blocks); 
    }

});
