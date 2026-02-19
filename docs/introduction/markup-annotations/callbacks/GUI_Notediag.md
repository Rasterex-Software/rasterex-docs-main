Connection callback that is called when the note tool is used.

### Additional Methods
- **setText(text)**: Sets the text to be displayed in the note dialog.
- **isAvailable()**: Returns true if a note is selected; otherwise, false.
- **getText()**: Returns text of the selected note.

### Callback Parameters
- `Notedata`: **String** - the text of the note.
- `Readonly`: **Boolean** - if the text in the note is read-only this value is `true`.

### Example

```javascript
RxCore.GUI_Notediag.connect(function (Notedata, Readonly) {

    console.log("the text of the note", Notedata);
    console.log("read only", Readonly);

  
});
```