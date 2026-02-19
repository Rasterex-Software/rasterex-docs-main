Connection callback called when a vector layer visibility state is changed.

### Callback Parameters
- `layer`: **vector layer object** - The vector layer that was changed.

```javascript
layer {
    index: number; // index of layer
    name: string; // name of layer
    state: Boolean; // display on/off
    color: color; // layer color
}
```
### Example

```javascript

    RxCore.GUI_VectorLayerVisibilityChange.connect(function(layer){

        console.log("vector layer ", layer.name, " state changed to ", layer.state );

    });

```