Imports a set of pages from a PDF source document to a currently open target PDF document.


### Syntax

```typescript

        // imports a set of pages

        RxCore.importPages(file, pageRange, pageArray, isReplace, count).then(() => {
            
            console.log("pages replaced");
            
        }).catch(() => {
            console.log("page replace failed");
        })




```

### Parameters


- `file`: **File object** — File objects are generally retrieved from a FileList object returned as a resul of a user selecting files using the "\<input\>" element, or from a drag and drop operation's DataTransfer object. In this case it is the PDF source file to extract pages from.

- `pageRange`: **Double Array of numbers** — A range of pages to replace with new pages from the PDF file.

- `pageArray`: **Double Array of numbers** — A range of pages to extract from the selected PDF file.

- `isReplace`: **boolean** — if true the method is used to replace pages in a target document,

- `count`: **number** — The end index of the range of pages to replace or insert into the target document.

Optional

- `width`: **number** — If this is a new blank page this is the width of that page. 

- `heigth`: **number** — If this is a new blank page this is the heigth of that page.


### Returns

- **Promise** — This method returns a promise.
