Connection object that returns the applied calibration value and page number when a calibration value is applied to a page.

### Associated methods
- [RxCore.calibrate](../methods/calibrate.md)


### Callback Parameters
- `calibratedata`: **object**: Object containing the calibration value and page number.

```javascript
var calibratedata = {
    calibratescale: nCalibrateScale, //number
    pagenumber: pagenumber //number
};
```

### Example

```javascript
    RxCore.GUI_CalibrateComplete.connect(function(calibratedata){
         console.log("Page ", calibratedata.pagenumber, " has new calibration scale ",  calibratedata.calibratescale);   
    });

```