Some files may have an internal coordinate system that does not match the visible information in the drawing.
In those cases this method can be called to convert an internal metric system to imperial. Then the drawing can be correctly calibrated using the calibration method. The method apply to the current page.


### Syntax

```typescript
RxCore.setPageCoordinateConvert(bConvert)
```

### Parameters

- `bConvert`: **boolean** — If true the coordinates for the page are converted.

### Returns

- **NA** — This method does not return a value.

### Example

```typescript
RxCore.setPageCoordinateConvert(true);
//Internal length values are divided by 25.4 to conform to imperial lengths.

```

