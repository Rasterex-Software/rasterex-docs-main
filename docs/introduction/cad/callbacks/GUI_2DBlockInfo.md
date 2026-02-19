This connection callback object returns an array of attributes for a selected vector block when the `RxCore.pickPolygon()` tool is used.

### Callback Parameters
- **partlist**: Array of attribute name-value pairs


### Example

```javascript
RxCore.GUI_2DBlockInfo.connect(function (partlist) {

    console.log("block information ", partlist);
   
  
});
```