

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

