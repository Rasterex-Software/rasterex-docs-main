This callback event returns information about a vector block, selected using the mouse,  when the [RxCore.getBlockInsert](../methods/getBlockInsert.md) tool is used in combination with [RxCore.blockhoverevent](../methods/blockhoverevent.md) turned on.

This callback can have two events set using either the stadard connect method or using a separate blockHoverCallback function.
The latter is used when there is no block under the mouse so the `result` will be `undefined`.

### Callback Parameters
- `result`: **object** — An object with information about the selected block.
- `mouse`: **object** — The mouse coordinates of the mouse position.

#### Example
```javascript

RxCore.GUI_2DBlockHover.connect(function(result, mouse){

    if (result) {
        

        const attributes = RxCore.getBlockAttributes(result.index);

        console.log(result, attributes);

      } 

});

RxCore.GUI_2DBlockHover.blockHoverCallback(function(result, mouse){


    if (!result) {
        
        console.log("no blocks found");

      } 


});


```