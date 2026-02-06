This connection callback object returns an array of attributes for a selected vector block when the mouse moves over a drawing. It must be enabled using [blockhoverevent](../methods/blockhoverevent)

### Callback Parameters
- **partlist**: Array of attribute name-value pairs
- **Screenpos**: Mouse x, y position
- **Pathindex**: Path index that can be used with methods like `addHoverforBlock`

### Example

```javascript
RxCore.GUI_2DBlockInfoPos.connect(function (partlist, Screenpos, Pathindex) {

    console.log("block pos ", Screenpos);
   
  
});
```
