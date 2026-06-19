---
title: Vector Entity
---

### The Vector Entity stucture.

The vector entity structure will vary depending on the vector type.


```typescript

// Line type
entity = {
    type : 0, //a number indicating the vector type,
    handle : //a unique value identifying the vector entity,
    typename : "LINE", //a string indicating the vector type,
    length : number, //the length of the line
    startpoint : {x:number , y: number},//the start point of the line, 
    endpoint : {x:number , y: number},  //the end point of the line, 
};

// poly line type
entity = {
    type : 1, //a number indicating the vector type,
    handle : //a unique value identifying the vector entity,
    typename : "LWPOLYLINE", //a string indicating the vector type,
    length : number, //the combined length of all lines in the poly line,
    area : number,//the area of the poly line, 
};

// Arc type
entity = {
    type : 4, //a number indicating the vector type,
    handle : //a unique value identifying the vector entity,
    typename : "ARC", //a string indicating the vector type,
    length : number, //the length of the arc
    radius : number,//the  radius of the arc, 
    sweep : number,  //the  anle of the arc in degrees, 
};

// Circle type
entity = {
    type : 5, //a number indicating the vector type
    handle : //a unique value identifying the vector entity.
    typename : "CIRCLE", 
    length : number, //the circumference of the circle
    radius : number,//the  radius of the circle, 
    area : number,  //the  area of the circle, 
};

// other types

entity = {
    type : number, //a number indicating the vector type,
    handle : //a unique value identifying the vector entity,
    typename : String, //a string indicating the vector type,
};


```

### The types

These are the currently possible vector entity types by type number.

```typescript

        switch(type){
            case 0 : sztype = "LINE";
            break;
            case 1 : sztype = "LWPOLYLINE";
            break;
            case 2 : sztype = "POLYLINE";
            break;
            case 3 : sztype = "SOLID";
            break;
            case 4 : sztype = "ARC";
            break;
            case 5 : sztype = "CIRCLE";
            break;
            case 6 : sztype = "TEXT";
            break;
            case 7 : sztype = "DIMENSION";
            break;
            case 8 : sztype = "MTEXT";
            break;
            case 9 : sztype = "VERTEX";
            break;
            case 10 : sztype = "ELLIPSE";
            break;
            case 11 : sztype = "POINT";
            break;
            case 12 : sztype = "3DFACE";
            break;
            case 13 : sztype = "3DSOLID";
            break;
            case 14 : sztype = "BODY";
            break;
            case 15 : sztype = "ATTDEF";
            break;
            case 16 : sztype = "ATTRIB";
            break;
            case 17 : sztype = "HATCH";
            break;
            case 18 : sztype = "IMAGE";
            break;
            case 19 : sztype = "INSERT";
            break;
            case 20 : sztype = "LEADER";
            break;
            case 21 : sztype = "MLINE";
            break;
            case 22 : sztype = "OLEFRAME";
            break;
            case 23 : sztype = "OLE2FRAME";
            break;
            case 24 : sztype = "RAY";
            break;
            case 25 : sztype = "REGION";
            break;
            case 26 : sztype = "SHAPE";
            break;
            case 27 : sztype = "SPLINE";
            break;
            case 28 : sztype = "TOLERANCE";
            break;
            case 29 : sztype = "TRACE";
            break;
            case 30 : sztype = "ACAD_PROXY_ENTITY";
            break;
            case 31 : sztype = "VIEWPORT";
            break;
            case 32 : sztype = "WIPEOUT";
            break;
            case 33 : sztype = "XLINE";
            break;
            default : sztype = "other type";
    
        }

```