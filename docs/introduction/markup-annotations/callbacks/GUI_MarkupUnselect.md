Connection callback that is called when a selected markup is unselected.


### Callback Parameters
- `Markup`: **object** - Markup object.

*See [markup object](../../markup-methods/intro) for information on properties and methods.*


### Example

```javascript
    RxCore.GUI_MarkupUnselect.connect(function (markup) {


        console.log("markup was un-selected", markup.markupnumber)

    
    });
```


