Connection callback event that is called when a page change occurs.

### Callback Parameters
- `pagingobject`:  **object** - An object containing information about the page change.

```javascript
pagingobject {
    numpages: number;   // Indicates total number of pages.
    currentpage: number; // Indicates current page.
}
```

### Example

```javascript
    RxCore.GUI_Page.connect(function (pagingobject){
        console.log("number of pages ", pagingobject.numpages);
        console.log("current page ", pagingobject.currentpage);

    });

```

