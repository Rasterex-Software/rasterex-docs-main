Connection object that is called when a file export is completed.



```typescript
    RxCore.GUI_exportComplete.connect(function (fileUrl) {
        window.open(fileUrl, '_new');
    });
```

### Callback Parameters
- **fileURL**: URL to the file created.