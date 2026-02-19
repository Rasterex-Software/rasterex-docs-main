This connection object displays information about a 3D part. The callback is triggered when the user interacts with the 3D model using the 3D select method.

### Callback Parameters
- `PartInfo` : **object**: This has the following properties:
  ```javascript
  Part3DObject {
      name: string; // Name of part
      attributes: array of name, value pairs
  }
  ```

### Example

```javascript
    RxCore.GUI_3DPartInfo.connect(function(PartInfo) {
        
        console.log(PartInfo.name, " was selected");
        
    });
```