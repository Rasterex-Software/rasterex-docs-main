This connection object is used in combinateion with a dialog or HTML element used for the calibration of drawing measurements.

### Associated methods
- [RxCore.calibrate](../methods/calibrate.md)


### Additional Methods
- **getUnitlabel()**: Returns the current unit postfix (e.g., mm, cm, inch) based on the setting.
- **setCalibration(val)**: Sets the current calibration value.
- **SetTempCal**: Sets a temporary calibration value.

### Callback Parameters
- `calibratedata`: **number**: The measured distance set with the calibration tool.


### Example

```javascript

    RxCore.GUI_Calibratediag.connect(function(calibratedata){
        
        console.log("calibrate distance", calibratedata);

    });

```
