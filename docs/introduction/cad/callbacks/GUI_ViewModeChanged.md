Callback event that is called when the CAD drawing view mode changes. View mode is the switching between monochrome and color display.

### Related method

- [setMonoChrome](../methods/setMonoChrome.md)



### Callback Parameters
- `onoff`: **boolean** — when `true` viewmode is on, when `false` viewmode is off.


#### Example
```javascript

RxCore.GUI_ViewModeChanged.connect(function (onoff){

    console.log("monochrome view is ", onoff);

});


```

