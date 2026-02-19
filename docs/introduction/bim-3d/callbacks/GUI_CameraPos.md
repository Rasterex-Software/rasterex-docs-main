This callback event returns the position of the 3D camera.

### Callback Parameters
- `Position`: **object**: Camera position x, y, and z coordinates.
- `CameraAngle`: **object**: Camera angle in radians.
- `ModelCenter`: **object**: Center of the model x, y, and z coordinates.

### Example
```javascript
    RxCore.GUI_CameraPos.connect(function(Position, CameraAngle, ModelCenter) {
        
        console.log("Camera position", Position, CameraAngle, ModelCenter);
        
    });
```