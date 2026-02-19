This method will return an array of layers for the currently active drawing and document if it contains vector layers.
If the document does not contain any layers the method will return undefined.


```javascript
    RxCore.getlayerlist();

```

### Parameters
- **None**: This method takes no parameters.


### Returns

- **Array of layer objects** — The layer object structure holds information on each layer.

### layer object

```javascript
layerobject {
    index: number; // index of layer
    name: string; // name of layer
    state: Boolean; // display on/off
    color: color; // layer color
}
```
