If a PDF document has pages added or removed this callback will return the new number of pages.

### Version
(Pro version only)

### Callback Parameters

- `numberofpages`: **number** — The number of pages in the currently active document after page remove or add.


### Example:

```javascript
RxCore.GUI_PageCountChanged.connect(onGetpagesnum);

function onGetpagesnum(numberofpages) {
    
    console.log("New number of pages are", numberofpages);
}

```
