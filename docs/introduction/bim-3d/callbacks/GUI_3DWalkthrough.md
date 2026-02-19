This connection object displays a 3D navigation element on top of the canvas, used for moving around within a 3D model.

### Additional Methods
- **setDivElement()**: Sets a DIV element to be used as a 3D navigation control.
- **setWalkthroughGUI(setvisible)**: Toggles the visibility of the 3D navigation control element.
  
### Callback Parameters
- `setvisible`: **boolean**: Indicating if the 3D navigation control element should be visible (`true`) or hidden (`false`).


### Example
```javascript
    RxCore.GUI_3DWalkthrough.connect(function(setvisible) {
        
        console.log(setvisible);
        
    });
```