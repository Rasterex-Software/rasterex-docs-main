Callback event called when setting alignment points in magnifier for compare/overlay magnified alignment. When the second point is aligned the alignment is complete.


### Return value
`npoint` - **number** - The point of the two point set currently aligned.


### Example

```typescript

RxCore.GUI_AlignPoint.connect(function(npoint){

    console.log("point ", npoint, " is aligned");

    if (npoint == 2){
        console.log("aligment complete");
    }

});

```