Connection callback called when a vector block visibility state is changed.


### Callback Parameters
- `blockobject`: **blockobject** - The block that was changed.

```javascript
blockobject {
    index: number; // index of block
    name: string; // name of block
    state: Boolean; // display on/off
}
```

### Example

```javascript

    RxCore.GUI_VectorBlockVisibilityChange.connect(function(block){

        console.log("block ", block.name, " state changed to ", block.state );

    });

```