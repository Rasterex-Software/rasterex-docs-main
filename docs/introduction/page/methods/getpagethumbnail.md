Returns a thumbnail object for the page.

### Syntax

```typescript
RxCore.getpagethumbnail(index)
```

### Parameters

- `index`: **number** — 0-indexed page number for which to get thumbnail.


### Returns



- **thumbnailobj** — Object with the following properties 

```typescript

{
                    created: **boolean** — true if the object has been created,
                    thumbnail: **HTML canvas** — Canvas for the thumbnail,
                    ctx: **HTML canvas context** — Canvas context for the thumbnail,
                    rotation: **number** — The rotation of the thumbnail in degrees,
                    image: **HTML Image** — Image for the thumbnail,
                    imageData: **Image data** — alternative base 64 string holding the image,
                    canvasSource: **HTML Image** — Image for the thumbnail,
                    source: **string** can be an image source url or null,
                    name: **string** name of the page,
                    number: **number** 0 indexed page number,
                    displaynum: **number** page number,

                    draw: function (ctx) { 
                        thisthumb.thumbctx = ctx;
                        thisthumb.draw_thumbnail();
                    }

}
```
