Has the same parameters as GUI_Markup but is only returned when markup is selected using the [selectmarkupbyindex](../methods/selectMarkUpByIndex) method.


### Example

```javascript
RxCore.GUI_MarkupIndex.connect(function (markup, operation) {

    if(markup != -1){

        // you can get markup object properties and call functions on the markup object here.
        console.log(markup.type, "type of selecte markup");
    }
  
});
```

*See [markup object](../../markup-methods/intro) for information on properties and methods.*

### Callback Parameters
- **Markup**: Markup object.
- **operation**: an object consisting of 3 booleans. created, modified, deleted 
