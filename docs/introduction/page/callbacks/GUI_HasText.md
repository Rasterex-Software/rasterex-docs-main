Connection callback that notifies if the opened file has searchable text.

### Callback Parameters
- **hastext**: Boolean that is true if the document has searchable text.

### Example

```javascript

    RxCore.GUI_HasText.connect(function(hastext){
        
        console.log("has text ", hastext);

    });

```
