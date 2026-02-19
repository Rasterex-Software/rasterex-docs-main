Connection callback that is called when a markup object is modified.


### Callback Parameters
- `Markup`: **object** - Markup object.
- `operation`: **number** - A number signifying the operation performed on the Markup object. 

*See [markup object](../../markup-methods/intro) for information on properties and methods.*

### Example

```javascript
RxCore.GUI_MarkupChanged.connect(function (Markup, operation) {

    //perform action on modified markup here.

    console.log("markup of type ", Markup.type, "modified");

  
});
```

