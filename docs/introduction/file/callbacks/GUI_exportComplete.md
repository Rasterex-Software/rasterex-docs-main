Connection object that is called when a file export is completed.

### Callback Parameters
- `fileURL`: **string** - URL to the file created.

### Example

```typescript
    RxCore.GUI_exportComplete.connect(function (fileUrl) {
        window.open(fileUrl, '_new');
    });
```

