---
title: Watermark
---

(Pro version only. Requires RxCore version 35.78 or newer.)

---

### Add Watermark

The viewer provides functionality to add text watermarks to PDF documents.  
You can add watermarks to all pages using the `addWatermarkToAllPages` method.

~~~js
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
~~~

---

### Add Watermark to a Single Page

~~~js
// Page number is 0-indexed, so pageNumber 0 = page 1
RxCore.addWatermarkToPage(pageNumber, "DRAFT", {
  position: "Center",
  rotation: 30,
  opacity: 50
});
~~~

---

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

### Add Render-Time Watermark (Dynamic)

*(Pro version only. Requires RxCore version **37.14** or newer.)*

The `addWatermarkRender` method adds a **temporary (render-only)** watermark to the active document viewer.  
This watermark is **not embedded** into the PDF and will **not appear** in exported or printed documents.  

NB! this can not be removed using the `removeWatermarkFromAllPages` method.

Use this for **dynamic, session-based, or user-specific** watermarks such as timestamps, usernames, or “For internal use only” labels.

#### Example

~~~js
async function applyWatermark() {
  const text = document.getElementById("wmText").value;
  const settings = {
    fontUrl: document.getElementById("wmFontUrl").value,   // Optional custom font URL (.ttf)
    fontName: document.getElementById("wmFontName").value, // Custom font name
    fontSize: parseInt(document.getElementById("wmFontSize").value, 10),
    color: document.getElementById("wmColor").value,       // e.g., "#FF0000"
    rotation: parseInt(document.getElementById("wmRotation").value, 10),
    opacity: parseInt(document.getElementById("wmOpacity").value, 10),
    scale: parseFloat(document.getElementById("wmScale").value),
    position: document.getElementById("wmPosition").value, // "Center", "TopLeft", etc.
    useRelativeScale: true,
    offsetX: 0,
    offsetY: 0,
    fontStyle: "normal"
  };

  const viewerCore = viewerFrame?.contentWindow?.RxCore;
  if (viewerCore && typeof viewerCore.addWatermarkRender === "function") {
    await viewerCore.addWatermarkRender(text, settings);
    console.log("✅ Watermark applied through iframe viewer.");
  } else {
    console.error("❌ RxCore.addWatermarkRender not available inside iframe.");
  }
}
~~~

#### Syntax

~~~js
await viewerCore.addWatermarkRender(text, settings);
~~~

#### Parameters

| Parameter | Type     | Description                                           |
| --------- | -------- | ----------------------------------------------------- |
| `text`    | `string` | The watermark text to display.                        |
| `settings`| `object` *(optional)* | Configuration for appearance and positioning. |

##### Supported Settings

In addition to the standard watermark options, the following extra fields are supported:

| Property          | Type     | Description                                   |
| ----------------- | -------- | --------------------------------------------- |
| `fontUrl`         | `string` | URL to a custom font file (e.g., `.ttf`).     |
| `fontName`        | `string` | Name of the custom font (used with `fontUrl`).|
| `fontSize`        | `number` | Font size in points.                          |
| `color`           | `string` | Font color as a hex string (e.g., `"#FF0000"`).|
| `rotation`        | `number` | Rotation angle in degrees.                    |
| `opacity`         | `number` | Opacity level (0–100).                        |
| `scale`           | `number` | Scale factor.                                 |
| `position`        | `string` | `"Center"`, `"TopLeft"`, etc.                 |
| `useRelativeScale`| `boolean`| If true, scales relative to page size.        |
| `offsetX` / `offsetY` | `number` | Manual X/Y offsets.                      |
| `fontStyle`       | `string` | `"normal"`, `"italic"`, or `"bold"`.          |

#### Returns
- **Promise** — Resolves when the watermark has been rendered successfully.

#### Notes
- The watermark is **render-only** and does **not modify** the PDF.  
- Useful for **temporary overlays**, **user tracking**, or **view-only confidentiality labels**.  
- To remove the render watermark:

  ~~~js
  await viewerCore.removeWatermarkRender();
  ~~~

- Compatible with RxCore running inside an iframe viewer.

---

### Remove Watermark

To remove all watermarks from the current PDF document, use the `removeWatermarkFromAllPages` method:

~~~js
// Remove all watermarks from the document
RxCore.removeWatermarkFromAllPages();
~~~

This removes any previously added watermarks from all pages.

---

### Automatically Add Watermark When Loading a File

You can use the `RxCore.GUI_FileLoadComplete` callback event to automatically apply a watermark when a file loads.

~~~js
RxCore.GUI_FileLoadComplete.connect(function(fileurl, activefile) {
  RxCore.addWatermarkToAllPages("CONFIDENTIAL");
});
~~~

---

### Export with PDF Watermark

To include changes such as added watermarks or page rotations, you should **not** use the `RxCore.exportFile` method when exporting the file.  
Instead, use the `RxCore.uploadPDF` method — it includes both watermarks and annotations.

~~~js
RxCore.uploadPDF();
~~~

This method uses a set of default export parameters.

You can control the export parameters using the `setDefaultExportParams` method.

---

### Syntax

~~~js
RxCore.setDefaultExportParams(consolidate, format, UPI, paperSize, markupFlag);
~~~

### Parameters

| Parameter     | Type      | Description                                                     |
| ------------- | --------- | --------------------------------------------------------------- |
| `consolidate` | `boolean` | Set to `true` to export only consolidated markup.               |
| `format`      | `string`  | Export format (e.g., `"PDF"`).                                  |
| `UPI`         | `string`  | Set to `"0"` (reserved for future use).                         |
| `paperSize`   | `string`  | Paper size for export (e.g., `"A4"`).                           |
| `markupFlag`  | `number`  | Export markup type: `0` for burned-in markup, `1` for native (PDF only). |

### Returns

- **N/A** — This method does not return a value.
