Connection callback called when a file containing vector layers is loaded.

### Additional Method
- **getHeight()**: Return the height of the canvas.

### Callback Parameters
- `vectorlayers`: **Array of vector layer objects** - The vector layers for the file.

```javascript
layerobject {
    index: number; // index of layer
    name: string; // name of layer
    state: Boolean; // display on/off
    color: color; // layer color
}
```
### Example

```javascript

    RxCore.GUI_VectorLayers.connect(function(vectorlayers){

        console.log("Number of vector layers", vectorlayers.length);

    });

```


