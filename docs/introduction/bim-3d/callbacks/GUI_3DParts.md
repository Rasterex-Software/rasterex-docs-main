This connection object lists parts in a 3D file. It is triggered when the user interacts with the 3D model using the 3D select method or opens a 3D file with parts.

### Callback Parameters
- `Parts`: **Array of objects** - Array of `Block3DObject` with the following properties:
  ```javascript
  Block3DObject {
      name: string; // Name of part
      index: number; // Part index
      state: Boolean; // Display on/off
      level: number; // List level
      position: number; // Position in the GUI display element in pixels.
      selected: Boolean; // Selected on/off.
  }
  ```
### Example

  ```javascript

    RxCore.GUI_3DParts.connect(function(Parts){

      console.log("this model has ", Parts.lenght, " parts");

    });
  
  ```