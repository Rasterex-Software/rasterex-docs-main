Add Watermark to a Single Page.

### Version
(Pro version only)


~~~js
// Page number is 0-indexed, so pageNumber 0 = page 1
RxCore.addWatermarkToPage(pageNumber, "DRAFT", {
  position: "Center",
  rotation: 30,
  opacity: 50
});
~~~


#### Watermark Options

The watermark function accepts two parameters:
- `text`: The text to display as watermark
- `settings`: An optional object containing watermark configuration

Available settings with their default values:

~~~js
{
  // Configuration settings
  useRelativeScale: true,
  /* 
  Determines if the scale is relative to the target page.
  If true, use "settings.scale" to control the text size.
  If false, use "settings.fontSize" to control the text size.
  Default: true
  */
  
  // Watermark Position and Layout
  position: "Center",   // Position of the watermark
  offsetX: 0,           // Horizontal offset from position
  offsetY: 0,           // Vertical offset from position
  scale: 1,             // Scale factor of the watermark
  rotation: 45,         // Rotation angle in degrees
  opacity: 100,         // Opacity percentage (0–100)

  // Text Properties
  font: 2,              // Font identifier
  fontSize: 20,         // Font size in points
  color: 0x000000,      // Text color in hexadecimal
  fontStyle: "normal",  // Font style
  flags: 2              // Watermark on top of content
}
~~~

---

### Font Table

| Enumerator            | Number | Font Name                                        |
| --------------------- | ------:| ------------------------------------------------ |
| courier               | 0      | Standard font: Courier.                          |
| courierBold           | 1      | Standard font: Courier-Bold.                     |
| courierBoldOblique    | 2      | Standard font: Courier-BoldOblique (Bold Italic).|
| courierOblique        | 3      | Standard font: Courier-Oblique (Italic).         |
| helvetica             | 4      | Standard font: Helvetica.                        |
| helveticaBold         | 5      | Standard font: Helvetica-Bold.                   |
| helveticaBoldOblique  | 6      | Standard font: Helvetica-BoldOblique (Bold Italic).|
| helveticaOblique      | 7      | Standard font: Helvetica-Oblique (Italic).       |
| timesRoman            | 8      | Standard font: Times-Roman.                      |
| timesBold             | 9      | Standard font: Times-Bold.                       |
| timesBoldItalic       | 10     | Standard font: Times-BoldItalic.                 |
| timesItalic 	        | 11     | Standard font: Times-Italic.                     |
| symbol 	            | 12     | Standard font: Symbol.                           |
| zapfDingbats 	        | 13     | Standard font: ZapfDingbats.                     |

---

### Position Values

Use these string values for the watermark position. These values are case-sensitive.

| String Value   | Position Description   |
| -------------- | ---------------------- |
| "TopLeft"      | Top left position      |
| "TopCenter"    | Top center position    |
| "TopRight"     | Top right position     |
| "CenterLeft"   | Center left position   |
| "Center"       | Center position        |
| "CenterRight"  | Center right position  |
| "BottomLeft"   | Bottom left position   |
| "BottomCenter" | Bottom center position |
| "BottomRight"  | Bottom right position  |

---

### Flags

| Enumerator | Number | Effect                                                 |
| ---------- | ------:| ------------------------------------------------------ |
| asContent  | 0      | Watermark becomes part of the page content.           |
| asAnnot    | 1      | Watermark is inserted as an annotation.               |
| onTop      | 2      | Watermark is displayed above other page content.      |
| unprintable| 3      | Watermark is not printed.                             |
| display    | 4      | Watermark is not displayed.                           |

---