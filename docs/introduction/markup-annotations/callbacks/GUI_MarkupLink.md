Callback event that returns the value of the link associated with a markup when the user clicks on a markup with a link enabled.

### Callback Parameters
- `MarkupObject`: **object** - The markup object that was clicked on.

*Use [markup.getLink().link](../../markup-methods/intro#getlink) to retrieve the link string value.*

### Example

```javascript
RxCore.GUI_MarkupLink.connect(function (MarkupObject) {


    var link = MarkupObject.getLink();
    
  
});
```

