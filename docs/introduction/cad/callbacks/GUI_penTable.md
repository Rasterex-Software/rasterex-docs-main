Connection callback called when the method  [RxCore.penTabledialog](../methods/penTabledialog.md) is called.

### Associated methods
- [RxCore.penTabledialog](../methods/penTabledialog.md)


### Callback Parameters
- **pentable**: Array of vector pen objects.

```javascript

    var pen = {
            penindex : number,
            arrayindex : number,
            originalcolor : string, //html color string
            color : string, //html color string
            originalstyle : number, // pen style 
            style : number, // pen style 
            penwidth : number, //pen width
            originalpenwidth : number, //pen width
            displaywidth : number, //pen width in display scale
            unitwidth : number, //pen width in unit scale
            
    }

    var pentable = {
        pens : array,
        getPen : function(index){} //returns a pen by index
    }
        


```

### Example of implementation.

```javascript

        function GUI_penTable(){

            RxCore.GUI_penTable.connect(onPentablereceived);

            function onPentablereceived(pentable, bactive){

                if(bactive){

                    setPenTableJSON(pentable);
                }
            }
        }

        function showPenTable(event, pentable){
            var PenData = [];
            
            var pentablelist = pentable;


            if(pentablelist){
                for (var pi = 0; pi < pentablelist.length;pi++){
                    
                     PenData.push({index : pentablelist[pi].penindex, width : pentablelist[pi].displaywidth, color : pentablelist[pi].color});

                    
                }
                //sortpens();
            }
    
        }


```
