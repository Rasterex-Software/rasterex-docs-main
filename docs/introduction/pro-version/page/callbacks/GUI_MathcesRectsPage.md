This callback event is triggered when `RxCore.getTextRects` is used with Foxit PDF.

### Version
(Pro version only)

### Callback Parameters

- `numMatches`: **object** - An object that contains a `matcharray` with the rectangle objects for the search.
- `CurrentPage` **number** - The page where the matches were found.

### Example:

```javascript
RxCore.GUI_MathcesRectsPage.connect(onGetMatches);

function onGetMatches(rects, currentpage) {
  var padding = { left: 5, top: 5, right: 15, bottom: 15 };

  if (rects.length > 0) {
    for (var ri = 0; ri < rects.length; ri++) {
      RxCore.markupLinkRect(
        true,
        rects[ri],
        currentpage,
        "[https://www.rasterex.com/](https://www.rasterex.com/)",
        padding
      );
    }
  }
}
```
