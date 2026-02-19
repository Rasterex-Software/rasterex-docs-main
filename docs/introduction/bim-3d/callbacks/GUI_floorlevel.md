This callback event returns a floor elevation object. This can be used with the `getfloorplanDocs` method to find an open drawing being used as a 2D navigation page for a floor in a 3D model.

### Callback Parameters
- `Floorindex`:  **number**: The floor level index.


### Example
```javascript
    RxCore.GUI_floorlevel.connect(function(Floorindex) {
        console.log("Floor ", Floorindex );
    });
```