This callback returns the list of 3D markups whenever there is a change.

### Callback Parameters
- `Markuplist`: **Array of objects** - Array of 3D meshes.
- `ActiveDoc`: **boolean** - `true` if the 3D document is active.


### Example

```javascript

    RxCore.GUI_3DMarkupList.connect(function(Markuplist, ActiveDoc){

      console.log(Markuplist, ActiveDoc);

    });
  
```