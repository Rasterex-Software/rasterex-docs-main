Connection callback called when a file containing vector blocks is loaded. This is called only once on the initial file load, whereas `GUI_VectorBlocks` is called when there is a change in vector block states.

### Additional Method

- **getHeight()**: Return the height of the canvas.

### Callback Parameters

- `vectorblocks`: **Array of vector block objects**: The blocks of the CAD file.

```javascript
blockobject {
    index: number; // index of block
    name: string; // name of block
    state: Boolean; // display on/off
}
```
### Example

```javascript

    RxCore.GUI_VectorBlocksLoaded.connect(function(vectorblocks){

        console.log(vectorblocks);

    });

```

