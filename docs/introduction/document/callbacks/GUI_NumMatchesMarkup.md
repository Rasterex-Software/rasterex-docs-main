This callback event is triggered when [RxCore.markupTextSearch](../methods/markupTextSearch.md) is used.

### Callback Parameters

- `numMatches`: **number**: Number of markups that match the search.

### Example:

```javascript
RxCore.GUI_NumMatchesMarkup.connect(onGetMatches);

function onGetMatches(numMatches) {
  console.log("found " + numMatches + " matches");
}
```
