This callback returns state information when the visibility of a 3D part is changed.

### Callback Parameters
- `PartInfo`: **object**: `Part3DObject` containing:
  ```javascript
  Part3DObject {
      name: string; // Name of part
      visible: Boolean; // State of visibility
  }
  ```

### Example
```javascript
    RxCore.GUI_3DPartState.connect(function(PartInfo) {
        if (partinfo.visible) {
            console.log("part is visible");
        } else {
            console.log("part is hidden");
        }
    });
```