Connection callback event that returns if a markup rxml file contains a scale object and when the load of this is complete.


### Callback Parameters

- **NA**: This callback does not return any values.

### Example

```javascript
    RxCore.GUI_scaleListLoadComplete.connect(function () {
        console.log("scale settings loaded");

    });
```