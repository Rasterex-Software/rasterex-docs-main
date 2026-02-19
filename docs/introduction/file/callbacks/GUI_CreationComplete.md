Used with `RxCore.createServerContent` method, this callback returns the XML created on the server when the content is created.

### Related methods
[RxCore.createServerContent](../methods/createServerContent.md)

### Callback Parameters
- `xml` **string**: A string holding the XML for the newly created content.

### Example
```javascript

    RxCore.GUI_CreationComplete.connect(function(xml){
        console.log("Data ", xml);
    });


```