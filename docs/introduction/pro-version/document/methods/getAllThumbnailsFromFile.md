Use this method to extract thumbnails from a PDF file.
The PDF would normally be a locally opened PDF file.

The method returns a Promise that when resolved returns and array of ImageData objects.

### Version
(Pro version only)


### Syntax example.

```typescript


    RxCore.getAllThumbnailsFromFile(file).then(value => {
        thumbnails = value;
        //value is an array of ImageData objects.
        
    }).catch(() => {
        console.log("Getting thumbnails failed")
    }) 



```

### Parameters
- **file** — A JavaScript File object normally obtained using a file open dialog.


### Returns
- **Promise** — Resolves when thumbnails are collected and returns these in a value object.