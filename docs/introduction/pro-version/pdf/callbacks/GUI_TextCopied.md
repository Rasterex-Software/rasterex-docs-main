This callback event returns the text when using the Foxit text selection tool.

### Version
(Pro version only)

### Callback Parameters
- **Original URL**: The URL of the document.
- **Text**: A string holding the selected text.

### Example:

```javascript
RxCore.GUI_TextCopied.connect(function(fileurl, text) {
    copyToClipboard(text).then(function() {
        console.log('OK');

    }).catch(function(error) {
        console.log('Failed');
    });
});
```