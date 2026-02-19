Connection callback used to connect markup text to an HTML input control.

### Additional Methods
- **getText()**: Returns the text of the selected text markup.
- **setText(text)**: Set the text of the selected text markup.

### Callback Parameters
- `textrect`: **object**: A rectangle object indicating the position and size of the markup text box.
- `operation`: **object**: Object with operation status values.

```javascript
operation = {
    start: false,
    create: false,
    edit: false,
    save: false
};
```
### Example

```javascript
    RxCore.GUI_TextInput.connect(function(textrect, operation)[

        if(operation.create){
            
            console.log("new text annotation created");

        }
    ]);
```

