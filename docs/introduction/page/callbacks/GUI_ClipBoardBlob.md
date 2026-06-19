This callback event returns a blob image data when using [RxCore.getClipRect()](../methods/getClipRect.md) and [RxCore.useClipboardCallback(true)](../methods/useClipboardCallback.md) has been called.

### Callback Parameters
- `imageblob`: **blob** - A blob with image data from the clipped rectangle.


### Example

```javascript

    RxCore.GUI_ClipBoardBlob.connect(function(imageblob){

        //assign an image or canvas to display the blob here.

    });

```
