Connection callback that is a high frequency update when markup object is modified.

### Callback Parameters
- `Markup`: **object** - Markup object.

*See [markup object](../../markup-methods/intro) for information on properties and methods.*


### Example

```javascript
RxCore.GUI_MarkupMeasureRealTimeData.connect(function (Markup) {

    console.log("markup type: ", Markup.type);
  
});
```
