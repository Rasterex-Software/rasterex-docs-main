---
title: Watermark
---

(Pro version only. Require RxCore version 35.78 or newer.) 


### Add Watermark

The viewer provides functionality to add text watermarks to PDF documents. You can add watermarks to all pages using the `addWatermarkToAllPages` method.

```javascript
// Add a simple watermark with default settings
RxCore.addWatermarkToAllPages("CONFIDENTIAL");

// Add a watermark with custom settings

    RxCore.addWatermarkToAllPages('Rasterex', {
      position: 'Center',
      offsetX: 0,
      offsetY: 0,
      scale: 1,
      opacity: 50,
      font: 4,
      rotation: 45
    });



```

### Add Watermark to a single page.

```javascript
//pagenumber is 0 indexed so pagenumber 0 = page 1
RxCore.addWatermarkToPage(pagenumber, "DRAFT", {
    position: "Center",
    rotation: 30,
    opacity: 50
});

```

#### Watermark Options

The watermark function accepts two parameters:
- `text`: The text to display as watermark
- `settings`: An optional object containing watermark configuration

Available settings with their default values:

```javascript
{
    //Configuration settings
    useRelativeScale : true 
     /* 
     useRelativeScale determine if the scale is relative to the target page.
     If it is true, use the "settings.scale" to control the text size.
     If false, use the "settings.fontSize" to control the text size.
     The default value is true.
     */
    
    // Watermark Position and Layout
    position: "Center",  // Position of the watermark
    offsetX: 0,         // Horizontal offset from position
    offsetY: 0,         // Vertical offset from position
    scale: 1,           // Scale factor of the watermark
    rotation: 45,       // Rotation angle in degrees
    opacity: 100,       // Opacity percentage (0-100)

    // Text Properties
    font: 2,            // Font identifier
    fontSize: 20,       // Font size in points
    color: 0x000000,    // Text color in hexadecimal
    fontStyle: "normal" // Font style
    flags: 2 //watermark on top of content
}
```

### Font table

| Enumerator            | number| Font name                                        |
| --------------------- |-------|--------------------------------------------------|
| courier               | 0 | Standard font: Courier.                              |
| courierBold           | 1 | Standard font: Courier-Bold.                         |
| courierBoldOblique    | 2 | Standard font: Courier-BoldOblique, Bold italic.     |
| courierOblique        | 3 | Standard font: Courier-Oblique, Italic.              |
| helvetica             | 4 | Standard font: Helvetica.                            |
| helveticaBold         | 5 | Standard font: Helvetica-Bold.                       |
| helveticaBoldOblique  | 6 | Standard font: Helvetica-BoldOblique, Bold italic.   |
| helveticaOblique      | 7 | Standard font: Helvetica-Oblique, Italic.            |
| timesRoman            | 8 | Standard font: Times-Roman.                          |
| timesBold             | 9 | Standard font: Times-Bold.                           |
| timesBoldItalic       | 10| Standard font: Times-BoldItalic.                     |
| timesItalic 	        | 11| Standard font: Times-Italic.                         |
| symbol 	            | 12| Standard font: Symbol.                               |
| zapfDingbats 	        | 13| Standard font: ZapfDingbats.                         | 	




### Position values
Use these string values for watermark position. These values are case sensitive.

| String value          |  Position               |
| --------------------- |------------------------ |
| "TopLeft"             | Top left position       |
| "TopCenter"           | Top center position.    |
| "TopRight"            | Top right position.     |
| "CenterLeft"          | Center left position.   |
| "Center"              | Center position.        |
| "CenterRight"         | Center right position.  |
| "BottomLeft"          | Bottom left position.   |
| "BottomCenter"        | Bottom center position. |
| "BottomRight"         | Bottom right position.  |


### Flags

| Enumerator     | number| Effekt                                               |
| ---------------|---|----------------------------------------------------------|
| asContent      | 0 | If set, the watermark will be a part of page content.    |  
| asAnnot        | 1 | If set, the watermark will be inserted as an annotation. |
| onTop          | 2 | If set, show watermark above other page content.         |
| unprintable    | 3 | If set, do not print a watermark.                        |
| display        | 4 | If set, do not display a watermark.                      |



### Remove Watermark

To remove all watermarks from the current PDF document, you can use the `removeWatermarkFromAllPages` method:

```javascript
// Remove all watermarks from the document
RxCore.removeWatermarkFromAllPages();
```

This will remove any previously added watermarks from all pages in the document.

### Automatic adding watermark when loading a file.
You can use the RxCore.GUI_FileLoadComplete callback event to automatically apply watermark when a file loads.

```javascript
        
        RxCore.GUI_FileLoadComplete.connect(function(fileurl, activefile){
            RxCore.addWatermarkToAllPages("CONFIDENTIAL");
        });
        
```

### Export with pdf watermark.
In order to include changes to the PDF like added watermark or page rotations, you should not use the RxCore.exportFile method when exporting the file. Instead use the method RxCore.uploadPDF. This will include both the added watermark and annotations.


```javascript
    RxCore.uploadPDF();

```
This method uses a set of default export parameters.

You can control the export parameters using this new method.

### Syntax

```javascript
    RxCore.setDefultExportparams(consolidate, format, UPI, paperSize, markupFlag);

```

### Parameters

- `consolidate`: **boolean** — Set to `true` to export only consolidated markup.
- `format`: **string** — Export format (e.g., `"PDF"`).
- `UPI`: **string** — Set to `"0"` (reserved for future use).
- `paperSize`: **string** — Paper size for export (e.g., `"A4"`).
- `markupFlag`: **number** — Export markup type: `0` for burned-in markup, `1` for native markup (PDF only).

### Returns

- **NA** — This method does not return a value.





