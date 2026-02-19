Connection object that implements an event used to control the compare alignment process.

### Callback Parameters
- `alignfile`: **number**: Integer indicating the stage of the CompareAlign process.


### Example

```typescript

RxCore.GUI_CompareAlign.connect(function(alignfile){

    console.log("File index ", alignfile);

});

```
