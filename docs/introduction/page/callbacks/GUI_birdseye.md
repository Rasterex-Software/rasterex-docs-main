This callback event returns a canvas with the current birdseye page representation when updated.

### Callback Parameters
- `pagenumber`: **number** - The 0-indexed page number.
- `Thumbnail`: **object** - An Rx thumbnail object containing the image canvas.

### Example

```javascript

    RxCore.GUI_birdseye.connect(function(pagenumber, Thumbnail){

        var mybirdseyecanvas = document.createElement('canvas');
        var ctx = mybirdseyecanvas.getContext('2d');

        mybirdseyecanvas.width = Thumbnail.thumbnail.width;
        mybirdseyecanvas.height = Thumbnail.thumbnail.height;


        RxCore.markUpRedraw();

        Thumbnail.draw(ctx);

});

```
