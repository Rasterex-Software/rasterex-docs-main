Connection callback that is called when a page has been loaded.

### Callback Parameters

- `Pagenumber`: **number**: 0-indexed page number.


### Example

```javascript

    RxCore.GUI_pageLoadComplete.connect(function(Pagenumber){
        console.log("Page loaded " Pagenumber + 1);

    });

    
```