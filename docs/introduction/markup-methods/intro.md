---
title: Markup Object
---

Markup object is also referred to as annotation object. Information on these objects can be accessed using the following methods and properties.

Some callbacks return a single or an array of markup objects. 

## Markup Properties

```javascript
Markup {
    x : number; // left position of the markup object
    y : number; //top position of the markup object
    w : number; //right position or width depending on type
    h : number; //bottom position or height depending on type

    xscaled : number; // left position of the markup object in current view coordinates,
    yscaled : number; //top position of the markup object in current view coordinates,
    wscaled : number; //right position or width in current view coordinates, depending on type
    hscaled : number; //bottom position or height in current view coordinates, depending on type

    points : array of number //the point coordinates for annotations like area, polygon and polyline

    type: number; // markup type
    subtype: number; // markup subtype
    alternative: number; // markup alternative
    color: color; // markup color
    comments: array of comment objects //the array that holds the comments associated with the markup object.
    consolidated : boolean; //true if the markup has the consolidated flag set.
    fontname: string; // font name
    linewidth: number; // width of markup object
    signature: string; // name of the user who created the markup
    markupnumber: number; // unique number for the current markup set
    dimtext: string; // value for measurement markups
    layer: number; // markup layer
    pagenumber: number; // 0-indexed page number for markup placement
    text: string; // value for text markups
    bisTextArrow: boolean; //true if the markup is an arrow for a callout.
    bUseFixedScale : boolean; //Boolean value that affects how line thickness and labels are displayed.
    bCanHaveLink : boolean; // if true the markup type supports links.
    bhaveLink : boolean; // if true the markup has a link.
    linkURL : string // if the markup has a link this property holds the link address.
    hidevaluelabel : boolean; // if true and the markup has a label the label is not rendered.
    transparency: number; //a value between 0 and 100 that holds the transparency value
    rotation: number; //the rotation of the markup in degrees.
    uniqueID: string; // A unique identity for the markup object.
    textBoxConnected: markupobject; //if the markupobject is an arrow for a callout this is the connected text box connected to it.
    font: font object;
    status : string; //a status string that can be used to set a status on the annotation object.
    ismeasure : boolean; //if true the markup object is one of the types used for measurement.
}
```

---

## Markup Object Methods

### AddAttribute

Adds custom attributes to the markup, retained when saved to file.

- **Syntax**: `Markup.AddAttribute(szName, szValue)`
- **Parameters**:
  - `szName`: Attribute name
  - `szValue`: Attribute value
- **Returns**: None
- **Usage Caution**: This can permanently alter the markup if saved.

---

### updateAttribute

Updates a custom attributes on the markup, retained when saved to file.

- **Syntax**: `Markup.updateAttribute(szName, szNewValue)`
- **Parameters**:
  - `szName`: Attribute name
  - `szNewValue`: The new Attribute value 
- **Returns**: None
- **Usage Caution**: This can permanently alter the markup if saved.

---


### AddComment

Adds a comment to the markup, retained when saved to file.
markup.comments.length, sign, this.note[markup.markupnumber], timestamp

- **Syntax**: `Markup.AddComment(id, signature, szComment, timestamp)`
- **Parameters**:
  - `id`: number, Comment id, normally the length of comments + 1.
  - `signature`: string,  The name or user id creating the comment.
  - `szComment`: string,  The comment string
  - `timestamp`: JavaScript time object,  Date and time for when the comment was added.
- **Returns**: None
- **Usage Caution**: This can permanently alter the markup if saved.

---

---

### deleteComment

Adds a comment to the markup, retained when saved to file.
markup.comments.length, sign, this.note[markup.markupnumber], timestamp

- **Syntax**: `Markup.deleteComment(id)`
- **Parameters**:
  - `id`: number, Comment id used to identify the comment
- **Returns**: None
- **Usage Caution**: This can permanently alter the markup if saved.

---



### ClearAttributes

Clears all custom attributes from the markup.

- **Syntax**: `Markup.ClearAttributes()`
- **Parameters**: None
- **Returns**: None
- **Usage Caution**: This will remove all added attributes.

---

### GetAttributes

Retrieves the current custom attributes associated with the markup.

- **Syntax**: `Markup.GetAttributes()`
- **Parameters**: None
- **Returns**: Array of current custom attributes
- **Usage Caution**: Returns any attributes previously added.

---

### getcount

Returns the count value for count-type markups.

- **Syntax**: `Markup.getcount()`
- **Parameters**: None
- **Returns**: Count number
- **Usage Caution**: Only applicable to markups where count is relevant.

---

### getLink

Retrieves link information associated with the markup.

- **Syntax**: `Markup.getLink()`
- **Parameters**: None
- **Returns**: Object with link properties:
  - `bCanHaveLink`: Boolean indicating if the markup supports links
  - `link`: The actual link if set
  - `bhavelink`: Boolean indicating if the markup has a link

---

### getMarkupType

Gets a string describing the markup type.

- **Syntax**: `Markup.getMarkupType()`
- **Parameters**: None
- **Returns**: Object with properties:
  - `label`: Description of the markup type
  - `type`: Upper-case name of the type

---

### getrotatedPoint

Use to get screen coordinates transformed from a point on a rotated page.

- **Syntax**: `Markup.getrotatedPoint(x, y)`
- **Parameters**:
  - `x`: Horizontal component of original point
  - `y`: Vertical component of original point
- **Returns**: Object with properties:
  - `object {x : x, y : y}`:  Point in screen coordinate system


---


### getselected

Checks if the markup is currently selected.

- **Syntax**: `Markup.getselected()`
- **Parameters**: None
- **Returns**: Boolean, `true` if selected

---

### getUniqueID

Retrieves a unique ID of the markup, if set.

- **Syntax**: `Markup.getUniqueID()`
- **Parameters**: None
- **Returns**: Unique ID value for the markup

---

### Consolidate

Consolidate the markup based on settings.

- **Syntax**: `Markup.Consolidate(settingsobject)`
- **Parameters**:
  - `settingsobject`: Contains options for changing stroke color, text color, and layer.
  - **Returns**: None
- **Settings Object Structure**:

  ```javascript
  {
      changeStrokeColor: boolean,
      changeTextColor: boolean,
      changeLayer: boolean,
      strokecolor: html hex color,
      textcolor: html hex color,
      layer: integer
  }
  ```
---

### ConsolidateList

Adds markup objects to an array to consolidate them based on settings.

- **Syntax**: `Markup.ConsolidateList(settingsobject, last)`
- **Parameters**:
  - `settingsobject`: Contains options for changing stroke color, text color, and layer.
  - `last`: Boolean, starts consolidation if `true`
- **Returns**: None
- **Settings Object Structure**:

  ```javascript
  {
      changeStrokeColor: boolean,
      changeTextColor: boolean,
      changeLayer: boolean,
      strokecolor: html hex color,
      textcolor: html hex color,
      layer: integer
  }
  ```

---

### setLink

Associates a link with the markup object.

- **Syntax**: `Markup.setLink(link, bhavelink)`
- **Parameters**:
  - `link`: A string representing the link (e.g., a URL)
  - `bhavelink`: Boolean, set to `true` to activate the link
- **Returns**: None

---

### setUniqueID

Assigns a unique ID to the markup object.

- **Syntax**: `Markup.setUniqueID(ID)`
- **Parameters**:
  - `ID`: The unique ID to be set
- **Returns**: None

---

### setRxUniqueID

Sets a unique ID for the markup object using the RxView360 server method.

- **Syntax**: `Markup.setRxUniqueID()`
- **Parameters**: None
- **Returns**: None

---

### getMarkupType

Get the type description of the markup object.

- **Syntax**: `Markup.getMarkupType()`
- **Parameters**: None
- **Returns**: 
  ```javascript
  labelType = { type: string, label: string }
  ```

---

### getmarked

Checks if the markup object has the marked state, used to indicate selection by a user who does not own the markup object.

- **Syntax**: `Markup.getmarked()`
- **Parameters**: None
- **Returns**: Boolean, `true` if marked, `false` otherwise

---

### GetDateTime

Retrieves the creation date and time of the markup object.

- **Syntax**: `Markup.GetDateTime(time)`
- **Parameters**:
  - `time`: Boolean indicating if the returned string should include hours, minutes, and seconds
- **Returns**: A string with the date and time

---

### getJSONUniqueID

Retrieves a JSON representation of the markup object.

- **Syntax**: 
  ```javascript
  Markup.getJSONUniqueID(operation).then(function(jsondata) {
      const data = JSON.parse(jsondata);
  });
- **Parameters**:
  - `operation`: Object from the `GUI_Markup` event callback indicating if the markup was created, deleted, or modified
- **Returns**: Promise containing JSON data

---

### setdisplay

Turn the display of this markup object on/off

- **Syntax**: 
  ```javascript
      Markup.setdisplay(onOff);
  ``` 
- **Parameters**:
  - `onOff`: Boolean if true the markup is visible if false the markup is hidden.
- **Returns**: None

---

### zoomTo

Causes a zoom operation focusing on the markup object.

- **Syntax**: 
  ```javascript
      let padding = {x : 30, y : 30, w : 150, h : 150};
      Markup.zoomTo(padding);
  ``` 
- **Parameters**:
  - `padding`:  object that indicate the space around the markup to set the zoom factor too.
- **Returns**: None

---

### hidelabelmarkupobj

Sets the hidevaluelabel property of the markup object to false. When false the label, if it has one, is not rendered.

- **Syntax**: 
  ```javascript
      Markup.hidelabelmarkupobj();
  ``` 
- **Parameters**:
  - None
- **Returns**: None

---

### showlabelmarkupobj

Sets the hidevaluelabel property of the markup object to true. When true the label, if it has one, is rendered.

- **Syntax**: 
  ```javascript
      Markup.hidelabelmarkupobj();
  ``` 
- **Parameters**:
  - None
- **Returns**: None
