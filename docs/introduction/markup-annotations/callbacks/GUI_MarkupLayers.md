Connection callback that gives a list of markup layers. Called during `RxView360` startup.

### Additional Methods
- **getCurMarkupLayer()**: Returns the current markup layer.
- **getCanChangelayer()**: Returns true if layer changes can be performed.
- **SetLayerMarkupdisplay(numlayer, state)**: Set markup layer on/off.

### Callback Parameters
- **markuplayers**: Array of markup layer objects.

```javascript
Layers {
    Layer: number; // Layer index
    Name: string; // Layer name
    Color: color; // Layer color
    display: Boolean; // On/off
}
```

### Example

```javascript
RxCore.GUI_MarkupLayers.connect(function (markuplayers) {

    console.log("Number of markup layers: ", markuplayers.length);
  
});

var currentmlayer = RxCore.GUI_MarkupLayers.getCurMarkupLayer();

var bcanchangel = RxCore.GUI_MarkupLayers.getCanChangelayer();

if(bcanchangel){
    RxCore.GUI_MarkupLayers.SetLayerMarkupdisplay(4, false);
}




```



