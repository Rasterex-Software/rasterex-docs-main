Returns a canvas when the `get3dFloorplanCanvas` method is used. Use the canvas to insert a floorplan plane into the 3D drawing using the `create3DfloorplanfromCanvas` method.

### Callback Parameters
- `Floornum`: **number**: Floor number.
- `Canvas`: **canvas**:  The HTML5 Canvas.
- `Alignarray`: **array**: Array of alignment data created when creating a compare overlay.

### Example

```javascript
    RxCore.GUI_FloorplanCanvas.connect(function(Floornum, Canvas, Alignarray) {
        
        console.log("Floor canvas for floor ", Floornum );

    });
```