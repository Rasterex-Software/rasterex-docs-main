This connection callback object provides information about the currently selected 3D markup object. It is called when the user interacts with the 3D model using the 3D select markup method.

### Callback Parameters
- `MarkupInfo`: **object** - Containing attribute name-value pairs.

### Example

```javascript

    RxCore.GUI_3DMarkupInfo.connect(function(MarkupInfo){

      console.log(MarkupInfo, Reason);

    });
  
```