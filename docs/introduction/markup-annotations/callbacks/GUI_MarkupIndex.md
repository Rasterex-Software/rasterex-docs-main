Has the same parameters as GUI_Markup but is only returned when markup is selected using the [selectmarkupbyindex](../methods/selectMarkUpByIndex) method.


### Callback Parameters
- `markup`: **object** or **number** - Selected markup object or -1 if no object selected.
- `operation`: **object** - an object consisting of 3 booleans. created, modified, deleted .

*See [markup object](../../markup-methods/intro) for information on properties and methods.*


### Example

```javascript
RxCore.GUI_MarkupIndex.connect(function (markup, operation) {

    if(markup != -1){

        // you can get markup object properties and call functions on the markup object here.
        console.log(markup.type, "type of selecte markup");
    }
  
});
```
