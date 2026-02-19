This connection callback object lists information about the currently selected 3D markup object. It is triggered when the user interacts with the 3D model using the 3D select markup method, deletes a 3D markup, or creates a new 3D markup.

### Callback Parameters
- `MarkupInfo`: **object** - Containing attribute name-value pairs.
- `Reason`: **object** - Object with properties indicating the action taken:
  - **Created**: Boolean
  - **Modified**: Boolean
  - **Deleted**: Boolean

### Example

```javascript

    RxCore.GUI_3DMarkup.connect(function(MarkupInfo, Reason){

      console.log(MarkupInfo, Reason);

    });
  
```
