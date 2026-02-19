Connection callback that notifies when the scaling of a page has changed.

### Callback Parameters
- `fileindex`: **number** - The index of the file that had the page scale changed.
- `pagenumber`: **number** - The 0 indexed page number of the page that had the scale changed.
- `scaleObject`: **object** - An object that holds the scaling data.


See the full description of the [scaleObject](../../Scaling/ScalingObject.md) here.


### Example

```javascript

    RxCore.GUI_pageScale.connect(function(fileindex, pagenumber, scaleObject){
        console.log("scaling performed");

    });

    
```