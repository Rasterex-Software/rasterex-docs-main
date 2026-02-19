Callback returns a fill object when fill is applied or removed.

### Callback Parameters
- **Fillstyle**: A fill style object.

```javascript
Fillstyle {
    type: 'hatch'; // Type of fill
    name: HatchImage; // Name of the hatch image
    ptm: HatchImage; // Hatch image object
    tilesize: size; // Size of the tiles
    color: color; // Fill color
    description: szdescript; // Description of the fill style
    inuse: false; // Indicates if the fill style is currently in use
}
```

#### Example

```javascript

RxCore.GUI_HatchChange.connect(function(Fillstyle){

    console.log("Pattern applied ", Fillstyle.description);

});

```