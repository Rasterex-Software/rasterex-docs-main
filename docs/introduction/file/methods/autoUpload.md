This is a method switch that determine if a uploaded file is opened in the viewer automatically.

### Syntax

```typescript
    RxCore.autoUpload(onoff);
```

### Parameters

- `onoff`: **boolean** - If `true` uploaded files are loaded automatically, if `false` the integration have to use the [GUI_UploadComplete](../callbacks/GUI_UploadComplete.md) callback event to open the file. 

### Returns

- **NA** — This method does not return a value.