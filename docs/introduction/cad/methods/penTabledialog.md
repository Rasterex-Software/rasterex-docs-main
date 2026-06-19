Used to trigger a callback returning the current pen table for the active file if supported by the format.


### Associated callbacks



### Syntax

```typescript
RxCore.penTabledialog();
```



### Parameters

- **none**: this method does not take any parameters.

### Returns

- **NA** — This method does not return a value.


```javascript

    var pen = {
            penindex : number,
            arrayindex : number,
            originalcolor : string, //html color string
            color : string, //html color string
            originalstyle : number, // pen style 
            style : number, // pen style 
            penwidth : number, //pen width
            originalpenwidth : number, //pen width
            displaywidth : number, //pen width in display scale
            unitwidth : number, //pen width in unit scale
            
    }

    var pentable = {
        pens : array,
        getPen : function(index){} //returns a pen by index
    }
        


```