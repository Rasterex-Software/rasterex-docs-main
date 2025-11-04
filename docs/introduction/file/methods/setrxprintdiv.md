Use this method to set up a div in the main html to be used for printing.


### Syntax


```typescript

let printdiv = document.getElementById('myprintdiv');

RxCore.setrxprintdiv(printdiv)
```

### Parameters

- `printdiv`: **HTML DOM element** — The DOM element to use for printing.

### Returns

- **NA** — This method does not return a value.


In order for this to work correctly you will need to create a CSS @media print section that includes the print div but hides the other html elements and make sure the print div is included in the print media but not displayed on screen.


### CSS example

```CSS

@media print {
    body * {
        display: none;
        
    }

    #printdiv, #printdiv * {
        display: block;
        
    }
}

@media screen {
    #printdiv, #printdiv * {
        display: none;
        
    }
}
```
