This callback event returns information about a vector entity, selected using the mouse,  when the [RxCore.getVectorEntity](../methods/getVectorEntity.md) tool is used in combination with [RxCore.blockhoverevent](../methods/blockhoverevent.md) turned on.

### Callback Parameters
- `vectorinfo`: **object** — information about the selected vector entity. Block if part of a block, the vector layer, the Entity property is an object that can contain different information depending on the vector type.

- `screenmouse`: **object** — The mouse coordinates of the mouse click.
- `pathindex`: **number** — The vector index.

#### Example
```javascript

RxCore.GUI_2DEntityInfoScreen.connect(function(vectorinfo, screenmouse, pathindex){

    if(pathindex.index){

        let messagetext = 'Type: ' +  vectorinfo.Entity.typename + '<br>' +

        'Layer: ' + vectorinfo.Layername;


        if(vectorinfo.Block != undefined){

          if(vectorinfo.Block.listed){


            const attributes = RxCore.getBlockAttributes(vectorinfo.Block.index);
            
            const tag = attributes.length > 0 ? '<br>Attribute: Yes' : '';

  
            messagetext = 'Type: ' +  vectorinfo.Entity.typename + '<br>' +

            'Block: ' + vectorinfo.Block.name + tag + '<br>' +
            'Layer: ' + vectorinfo.Layername;
  
          }else{
            messagetext = 'Type: ' +  vectorinfo.Entity.typename + '<br>' +
            'Layer: ' + vectorinfo.Layername;
    
          }
  
        }
        if(vectorinfo.Entity.length != undefined && !isNaN(vectorinfo.Entity.length)){
          messagetext = messagetext + '<br> Length: ' + vectorinfo.Entity.length.toFixed(2);
        }
        if(vectorinfo.Entity.area != undefined && !isNaN(vectorinfo.Entity.area)){
          messagetext = messagetext + '<br> Area: ' + vectorinfo.Entity.area.toFixed(2);
        }

        if(vectorinfo.Entity.sweep != undefined && !isNaN(vectorinfo.Entity.sweep)){
          messagetext = messagetext + '<br> Sweep Angle: ' + vectorinfo.Entity.sweep.toFixed(2);
        }


        if(vectorinfo.Entity.radius != undefined && !isNaN(vectorinfo.Entity.radius)){
          messagetext = messagetext + '<br> Radius: ' + vectorinfo.Entity.radius.toFixed(2);
        }

        console.log(messagetext);

        
      }      

});


```

