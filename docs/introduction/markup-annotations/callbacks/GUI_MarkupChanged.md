Connection callback that is called when a markup object is modified.


### Example

```javascript
RxCore.GUI_MarkupChanged.connect(function (markup, operation) {

    //perform action on modified markup here.

    console.log("markup of type ", markup.type, "modified");

  
});
```

*See [markup object](../../markup-methods/intro) for information on properties and methods.*

### Callback Parameters
- **Markup**: Markup object.
- **operation**: a number signifying the operation performed on the Markup object. 
