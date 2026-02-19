Returns the label text of an Area or space markup when edited.

### Callback Parameters
- `dimtext` **string**: A string representing the label text.

### Example

```javascript
RxCore.GUI_MarkupAreaEdit.connect(function (dimtext) {

    console.log("Label", dimtext);
  
});
```
