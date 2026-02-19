Connection callback that notifies when a rotation operation has completed.

### Callback Parameters

- **degree**: The degree of rotation applied.
- **pagenumber**: The number of the page that has been rotated.

### Example

```javascript

    RxCore.GUI_RotatePage.connect(function(degree, pagenumber){
        console.log("page ", pagenumber + 1, " was rotated to ", degree, " degrees");

    });

    
```