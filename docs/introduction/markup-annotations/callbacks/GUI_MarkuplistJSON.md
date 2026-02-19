Callback event that returns a string that represents a list of all markup/annotations in JSON format for the currently active file.
The Callback is triggered using the [markupGetJSON](../methods/markupGetJSON) method.



### Callback Parameters
- `MarkupJSONlist`: **string** - A string containing the markups in JSON format.

### Example

```javascript
RxCore.GUI_MarkuplistJSON.connect(function (MarkupJSONlist) {

    console.log("JSON markup list ",  MarkupJSONlist);
   
  
});
```