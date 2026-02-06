Returns a list of open files.

### Syntax

```typescript
RxCore.getOpenFilesList()
```

### Parameters

- **None**

### Returns

- **openFilesList** — An array of objects with the current properties:
  - `Index`: Index of the file.
  - `name`: File name.
  - `isActive`: **boolean** — `true` if the file is currently active; otherwise, `false`.

### Example

```javascript

        var openfileslist = RxCore.getOpenFilesList();
        
        var openfiles = RxCore.getOpenFiles();

        var fileindex = 0;
        var ispdf = false;

        for(var ofl = 0; ofl < openfileslist.length ; ofl ++){
            if(openfileslist[ofl].isActive){
                fileindex = openfileslist[ofl].index;
            }
        }

        for(var of = 0; of < openfiles.length ; of ++){
            if(openfiles[of].index == fileindex){

                ispdf = openfiles[of].isPDF;
            }
        }

        if(!ispdf){
            hideAllIframes();
        }

        RxCore.setLayout(0, 0, false);
        RxCore.doResize(false,0, 0);

```