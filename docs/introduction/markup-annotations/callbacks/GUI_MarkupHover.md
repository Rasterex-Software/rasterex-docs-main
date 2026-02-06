Connection callback that is called when the mouse is moved over a markup object.


### Callback Parameters
- **Markup**: Markup object.

### Example

```javascript
RxCore.GUI_MarkupHover.connect(function (Markup) {

    console.log("markup type: ", Markup.type);
  
});
```


*See [markup object](../../markup-methods/intro) for information on properties and methods.*

