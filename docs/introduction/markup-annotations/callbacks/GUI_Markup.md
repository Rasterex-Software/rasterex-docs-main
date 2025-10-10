Connection callback that is called when a markup object is selected.


### Example

```javascript
RxCore.GUI_Markup.connect(function (markup, operation) {

    //if no markup was selected but just a click on canvas the markup has the value -1

    if(markup != -1){

        // you can get markup object properties and call functions on the markup object here.
        if (operation.created){
            console.log(markup.type, "Just created");
        }

    }

  
});
```

*See [markup object](../../markup-methods/intro) for information on properties and methods.*

### Callback Parameters
- **Markup**: Markup object.
- **operation**: an object consisting of 3 booleans. created, modified, deleted 
