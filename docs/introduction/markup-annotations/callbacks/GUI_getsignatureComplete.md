Connection object that is called when a signature image download is completed.


### Callback Parameters


- **signatureinfo** : Object that holds the download data.

```javascript
{

    data : singaturePNGData, // HTML image object
    width : img.width, // number, indicating widht of the image
    height : img.height, // number, indicating height of the image
    username : username, // string, a unique user name associated with the signature image
    initials : binitial // boolean, if true the image is for initials instead of full signature.
}
```

#### Example
```javascript
function GUI_getsignatureComplete() {
    RxCore.GUI_getsignatureComplete.connect(onGetSignature);
    
    function onGetSignature(signatureinfo) {

        // Perform operations on returned signature data here.
    }

}
```