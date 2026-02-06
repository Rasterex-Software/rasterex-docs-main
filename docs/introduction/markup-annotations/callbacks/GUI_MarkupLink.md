Callback event that returns the value of the link associated with a markup when the user clicks on a markup with a link enabled.

### Callback Parameters
- **MarkupObject**: The markup object that was clicked on.

### Example

```javascript
RxCore.GUI_MarkupLink.connect(function (Markup) {


    var link = Markup.getLink();
    
  
});
```



*Use [markup.getLink().link](../../markup-methods/intro#getlink) to retrieve the link string value.*