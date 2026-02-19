Callback event that returns the result of the `compareMeasure` method.

### Related methods
-  [RxCore.compareMeasure](../methods/compareMeasure.md)

### Callback Parameters
- `distance`:  **number**: The distance measured in document units.
- `angle`: **number**: Angle in radians of the two points of the distance measured.
- `offset`: **object**: Point object with x and y coordinates of the first point.
- `pagewidth`: **number**: Width of the measured page in pixels.
- `scaleinfo`: **object**: Extended object with addtional information.


```typescript
const measureobj = {dist: distance, angle : angle, offset : offset, pwidth : pagewidth, scaleinfo : scaleinfo};

```

```typescript
    RxCore.GUI_CompareMeasure.connect(function(measureobj){

        console.log("measured alignment" measureobj);

    });

```

