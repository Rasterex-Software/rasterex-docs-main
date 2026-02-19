Callback event that gives a list of markup objects when markup is changed and when the markup is initially loaded.

### Additional Methods
- **getDisplayName()**: Returns the markup signature for the current user.
- **getDisplayDate()**: Returns a date string for a given date JavaScript value.


### Callback Parameters
- `Markuplist`: **array of markup objects** The loaded markup objects in an array.

*See [markup object](../../markup-methods/intro) for information on properties and methods.*



### Example

```javascript
RxCore.GUI_Markuplist.connect(function (Markuplist) {

    console.log("There are ", Markuplist.length, "markup objects" );
   
  
});
```
