---
title: Collaboration mode
---

Collaboration mode is a special mode in Rasterex Web Viewer that exchanges annoations and measurements over a web socket between clients running in this mode.

### Prerequisites
In order to use collaboration you will need to install a web socket server.
You can use the web socket server included with our db back-end server.

You can get our db back-end from our github here.

### DB back-end
[https://github.com/Rasterex-Software/dbbackend](https://github.com/Rasterex-Software/dbbackend)

Check the included readme to get information on how to set this up.


### Static file
A static configuration file is included with the Rasterex Web Viewer installation.

`src\assets\config\UIConfig.js`

The `UIConfig.js` file provides a static configuration for the Viewer, enabling customization of its UI and functionality.

To set the viewer in collaboration mode the following settings will have to be changed.

Main setting that enables collabortion is "canCollaborate"


``` TypeScript

"canCollaborate": false,
//change to 
"canCollaborate": true,


```

We also recommend changing "showAnnotationsOnLoad".
This will make sure that all annotation types are visible when exchanged between clients.


``` TypeScript

"showAnnotationsOnLoad" : false,
//change to 
"showAnnotationsOnLoad" : true,


```

A typical UIConfig.js is listed below.


```JavaScript
var UIConfig = (function() {


    let ConfigJSON = {
         "UIConfig" : {
            
                "canFileOpen": true,
                "canSaveFile": true,
                "canGetFileInfo": true,
                "canPrint": true,
                "canExport": true,
                "canAnnotate": true,
                "canCompare": true,
                "canSignature": false,
                "canConsolidate": true,
                "convertPDFAnnots" : false,
                "createPDFAnnotproxy" : false,
                "canCollaborate": false,
                "canLogin" : true,
                "showmarkupZoom" : false,
                "alwaysShowScaling" : false,
                "showAnnotationsOnLoad" : false,
                "localStoreAnnotation": false,
                "disable2DVectorInfoButton" : false,
                "watermarkdemo" : false,
                "forceLogin" : false,
                "logoUrl": "assets/images/logo.svg",
                "dateFormat": {
                  "locale": "en",
                  "shortDate": "MMM d, yyyy",
                  "longDate": "MMMM d, yyyy",
                  "time": "h:mm a",
                  "month": "MMM",
                  "dateTime": "MMM d, yyyy h:mm a",
                  "dateTimeWithoutYear": "MMM d, h:mm a",
                  "dateMonthYear": "DD/MM/YYYY",
                  "dateTimeWithConditionalYear": "MMM d, [yyyy] h:mm a",
                  "dateTimeWithSeconds": "D/M/YYYY HH:mm:ss"
              }
        },
        "UIStyles" : [
            
                { "name": "accent", "value": "#31BD59" },
                { "name": "accent-secondary", "value": "#F0F7F9" },
                { "name": "main", "value": "#333C4E" },
                { "name": "secondary", "value": "#A4ABAE" },
                { "name": "light-secondary", "value": "#EDF1F2" },
                { "name": "background", "value": "#D6DADC" },
                { "name": "background-light", "value": "#F0F7F9" },
                { "name": "side-nav-background", "value": "#F0F7F9" },
                { "name": "side-nav-background-active", "value": "#FFFFFF" },
                { "name": "background-secondary", "value": "#F5F5F5" },
                { "name": "side-nav-color", "value": "#A6ADB0" },
                { "name": "side-nav-color-active", "value": "#31BD59" },
                { "name": "side-nav-panel-background", "value": "#FFFFFF" },
                { "name": "top-nav-background", "value": "#FFFFFF" },
                { "name": "top-nav-color", "value": "#333C4E" },
                { "name": "top-nav-background-active", "value": "#F0F7F9" },
                { "name": "top-nav-color-active", "value": "#333C4E" },
                { "name": "top-nav-border-bottom-color-active", "value": "transparent" },
                { "name": "toolbar-background", "value": "#FFFFFF" },
                { "name": "toolbar-color", "value": "#333C4E" },
                { "name": "toolbar-background-active", "value": "#31BD59" },
                { "name": "logo-height", "value": "auto" }
        ]
    };


    return {
        
        ConfigJSON : ConfigJSON

    };



})();

```




