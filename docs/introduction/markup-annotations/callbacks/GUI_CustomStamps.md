When creating custom stamps using the `RxCore.createCustomStamps` method, this callback event is called to notify of the custom stamp creation.

### Associated methods
- [RxCore.createCustomStamps](../methods/createCustomStamps.md)

### Callback Parameters
- `StampInfo`: **object**: An object that holds information on the created stamp and type of event.

```javascript
stampdata.type: // Type of event with values
    2: // stampdata.data = library name
    3: // stampdata.data = number of stamps
    5: // stampdata.data = stamp image object
stampdata.index = stamp name;
stampdata.width = stamp width;
stampdata.height = stamp height;
```

###  Example

```javascript

    RxCore.GUI_CustomStamps.connect(onCustomstamps);

    function onCustomstamps(StampInfo){

        //handle stamps here.  
              
    };



```

