This callback event returns the name of a 3D view when it is set as the active 3D view using `RxCore.restoreCameraByName`, once the view load is complete.

### Callback Parameters
- `Viewname` **string**: String containing the name of the activated 3D view.

### Example
```javascript
    RxCore.GUI_3DView.connect(function(Viewname) {
        
        console.log(Viewname, "activated");
        
    });
```
