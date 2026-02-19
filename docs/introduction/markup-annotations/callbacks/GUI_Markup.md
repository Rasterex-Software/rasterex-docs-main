Connection callback that is called when a markup object is selected.


### Callback Parameters
- `markup`: **object** or **number** - Selected markup object or -1 if no object selected.
- `operation`: **object** - an object consisting of 3 booleans. created, modified, deleted .

*See [markup object](../../markup-methods/intro) for information on properties and methods.*

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

