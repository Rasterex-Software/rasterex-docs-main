Use this method to get information from a currently open document usually used to maintain a recent document list that can be used to open files from a recent document list that include a thumbnail.

### Version
(Pro version only)


### Syntax example.

```typescript

    var FileInfo = RxCore.getCurrentFileInfo();

```

### Parameters
- **none** — This method does not take any parameters.


### Returns
- **object** — Returns an object with the following properties. 

- **object variant minimal** - For Documents where there are no valid thumbnail data

```typescript
                return {
                    path: FileName Source,
                    name: FileName,
                    date: Javascript date object,
                }
```

- **object variant image data** - For documents that has canvas based thumbnail image data.

```typescript
                return {
                    path: FileName Source,
                    name: FileName,
                    date: Javascript date object,
                    width: thumbmnail width,
                    height: thumbnailobj height,
                    buffer: canvas image buffer
                }
```
