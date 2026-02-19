This callback event is triggered when a zoom change has completed.

### Callback Parameters
- **Zoomparams**: Zoom operation parameters.

```javascript
Zoomparams {
    Type: 0; // Zoom in
    Type: 1; // Zoom out
    Type: 2; // Zoom window
    Type: 3; // Zoom all
    Type: 4; // Zoom width
    Type: 5; // Zoom height
}
```

These can be used directly with the `zoomPageUpdate` method.

```javascript
    RxCore.GUI_ZoomUpdated(function(zoomparams, type) {

        console.log("params " zoomparams);
        console.log("type " type);

    });

```


