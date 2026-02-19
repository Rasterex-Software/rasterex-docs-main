Callback event called when setting alignment points in magnifier for compare/overlay magnified alignment is complete.


### Return value
`npoint` - **number** - The point of the two point set currently aligned.


### Example

```typescript

RxCore.GUI_AlignPointComplete.connect(function(npoint){

    console.log("point ", npoint, " is aligned");

});

```