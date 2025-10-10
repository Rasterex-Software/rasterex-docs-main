Connection object that is called when a signature image upload is completed.


, binitial
### Callback Parameters
- **username**: String - A unique value that identify the signature associated user.
- **binitial**: Boolean - If true the upload is for initials instead of full signature.


#### Example
```javascript
function GUI_putsignatureComplete() {
    RxCore.GUI_putsignatureComplete.connect(onPutSignature);
    
    function onPutSignature(username, binitial) {

        // Perform operations when upload is complete.
    }

}
```