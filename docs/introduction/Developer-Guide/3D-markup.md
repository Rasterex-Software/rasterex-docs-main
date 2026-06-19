---
title: Annotations on 3D models
---

3D annotations in RxCore are created on a fixed 3D camera view. When 3D markup mode is enabled, the current camera position is saved and annotations can be added to that view.

This makes it possible to restore the same model orientation later and display the associated annotations in the correct context.

Each 3D annotation is associated with a saved camera view.


## Create a 3D markup view

To begin adding annotations to a 3D model, create a 3D markup view.
This freezes the current 3D camera view and allows annotations to be placed on that saved view.

[RxCore.create3DMarkup(true)](../bim-3d/methods/create3DMarkup.md).

```js

RxCore.create3DMarkup(true);

```

## Receive the saved 3D camera

When the 3D markup view is created, the saved camera is returned through the [RxCore.GUI_3DCameraSave](../bim-3d/callbacks/GUI_3DCameraSave.md) callback event.

```js

RxCore.GUI_3DCameraSave.connect(function(camera, fileActive) {
  if (!fileActive) return;

  console.log("Saved 3D camera:", camera);

  const resetView = RxCore.get3DResetView();

  if (resetView && camera.name === resetView.name) {

    drawTopViewThumbnail(resetView);
    RxCore.reset3DModel();  

  } else {
    RxCore.restoreCameraByName(camera.name);
  }
});

```

## Reset to the default 3D view

Calling [RxCore.reset3DModel](../bim-3d/methods/reset3DModel.md) will reset the model view to the default view.

## Thumbnail for the 3D view

You can get the thumbnail image using the camera name and the [RxCore.getCameraimage](../bim-3d/methods/getCameraimage.md) Method.

```js

// Draw the thumbnail for the default (reset) 3D view
function drawTopViewThumbnail(resetView) {
  if (!resetView) return;

  const canvas = document.getElementById(resetView.name); // The UI canvas element to draw the thumbnail on.
  const cameraImage = RxCore.getCameraimage(resetView.name);

  if (!canvas || !cameraImage) return;

  canvas.style.cursor = "pointer";
  canvas.width = cameraImage.width;
  canvas.height = cameraImage.height;

  const ctx = canvas.getContext("2d");
  ctx.drawImage(cameraImage.thumbnail, 0, 0);

  RxCore.drawmarkupToCanvas(ctx, canvas.width, canvas.height, resetView.name);
}

```

## Restoring a 3D view

The returned camera object can be used to restore the saved view later and to generate a thumbnail for that view.

To display annotations associated with a saved 3D view, restore the camera using: [RxCore.restoreCameraByName(name)](../bim-3d/methods/restoreCameraByName.md) 


The callback event [RxCore.GUI_3DView](../bim-3d/callbacks/GUI_3DView.md) is triggered when a 3D view becomes active.  
It returns the name of the active view so your UI can be updated accordingly.

```js


RxCore.GUI_3DView.connect(function (viewname){

            var cnvgrop = document.getElementsByClassName('views3D');

            for(var i = 0; i < cnvgrop.length ; i++){
                cnvgrop[i].style.border = 'none';
            }

            if(viewname != null){

                //mark the thumbnail for the selected view with a thicker border.

                if(document.getElementById(viewname) != null){
                    document.getElementById(viewname).style.border = "thick solid #0000FF";
                }
                
            }

});

```

## 3D markup list

The callback event [RxCore.GUI_3DMarkupList](../bim-3d/callbacks/GUI_3DMarkupList.md) returns the available 3D markup data for the active file.
Top-level camera items in the returned data represent saved 3D views that can be restored and used to display their associated annotations.


## Supported annotation types

Standard measurement tools will not work with 3D models like arcs, angles and area.

A separate 3D distance tool is available and uses the same [RxCore.markUpDimension](../markup-annotations/methods/markUpDimension.md) method call that is used to create dimension lines in 2D formats.

## Restore view by annotation selection

When calling [RxCore.selectMarkUpByIndex](../markup-annotations/methods/selectMarkUpByIndex.md) and the annotation is associated with a 3D view, that view will automatically be restored and made active.

A separate selection method for 3D measurement exists called [RxCore.select3DMarkUpByID](../bim-3d/methods/select3DMarkUpByID.md).


## Storing custom attributes

It is possible to store custom attributes associated with each 3D view using [RxCore.add3DViewAttribute](../bim-3d/methods/add3DViewAttribute.md). These attributes can be used to store additional information associated with that view.

These attributes can be modified later using [RxCore.update3DViewAttribute](../bim-3d/methods/update3DViewAttribute.md).
 

## Summary

3D markup in RxCore is based on saving camera views and attaching annotations and metadata to those views. By restoring a saved camera, the associated annotations can be displayed in the correct context.

Using the provided callbacks and methods, you can build custom workflows for reviewing, annotating, and managing 3D data.

