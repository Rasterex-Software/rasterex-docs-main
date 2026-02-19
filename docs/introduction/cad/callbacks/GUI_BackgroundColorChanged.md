Callback event that is called when the CAD drawing background color changes.


### Related method

- [toggleBackground](../methods/toggleBackground.md)


### Callback Parameters

- `color`: **string** — the html color currently active.

#### Example
```javascript

    RxCore.GUI_BackgroundColorChanged.connect(function (color){

        console.log("color changed to ", color);

    });


```