Callback event that triggers when a file is loaded using `open3DFloorplanPage`.

### Callback Parameters
- `FileName`: **string** - Filename.
- `Active`: **boolean** - `true` if the file is active.
- `Docpage`: **object** - An object representing the Docpage.

### Docpage
```javascript
docpage {
    docindex: integer; // Open file index
    pageindex: integer; // Page index
    floorindex: integer; // 3D model floor index
}
```
### Example

```javascript
    RxCore.GUI_floorLoadComplete.connect(function(FileName, Active, Docpage) {
        console.log("Floor loaded ", FileName );
    });
```