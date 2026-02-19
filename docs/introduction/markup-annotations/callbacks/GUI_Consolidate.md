Connection object that is called when consolidation is turned on using `RxCore.consolidate(true)`.

### Related methods
- [RxCore.consolidate](../methods/consolidate.md)

### Callback Parameters
- `consolidateObj`: **object**: Object containing consolidation state information.

```javascript
consolidateObj {
    isactive: Boolean // Indicates if consolidation is on or off.
}
```

###  Example

```javascript
    RxCore.GUI_Consolidate.connect(function(consolidateObj){

        if(consolidateObj.isactive){
            console.log("Consolidate active");
        }

    });

```


