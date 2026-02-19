This callback event notify when all blocks are un-selected. 

### Related method

- [unselectAllBlocks](../methods/unselectAllBlocks.md)


### Callback Parameters
- **none**: This callback does not return any values.

#### Example
```javascript

RxCore.GUI_2DBlockUnselectAll.connect(function(){

    console.log("All blocks un-selected");        

});
