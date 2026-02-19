This callback event returns information about a vector block, selected using the mouse,  when the 
[RxCore.getBlockInsert](../methods/getBlockInsert.md) tool is used.


### Callback Parameters
- `block`: **object** — An object with information about the selected block.


#### Example
```javascript

RxCore.GUI_2DBlock.connect(function(block){

    if (block) {
        

        const attributes = RxCore.getBlockAttributes(block.index);

        console.log(block, attributes);        

      } 

});


```