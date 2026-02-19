In RxCore, both pages and markup/measurement objects have an associated scaling object.

Listed below is the full class description of the scaling object with properties and methods.


```javascript

class ScaleObject {
            constructor() {
                var thisscale = this;                
                                            
                this.measurescale = MeasureScale;
                this.Unitofmeasure = Unitofmeasure;
                this.unitname = "Metric";
                this.SubmeasureUnit = SubmeasureUnit;
                this.Unitlabel = Unitlabel;
                this.AreaUnitlabel = AreaUnitlabel;
                this.unitscale = unitscale;
                this.scaleValue = "1:1";
                this.scaleLabel = "1 Millimeter : 1 Millimeter";

                this.ndimprecision = ndimprecision;

                
                this.setUnit = function(value){

                
                        switch (value) {
                            case 1:
                                this.Unitlabel = "mm";
                                this.AreaUnitlabel = "mm\u00B2";
                                break;
                            case 2:
                                this.Unitlabel = "in.";
                                this.AreaUnitlabel = "sq.in.";
                                break;
                            case 3:
                                this.Unitlabel = "Units";
                                this.AreaUnitlabel = "Units\u00B2";
                                break;
                        }
                        this.Unitofmeasure = value;
                    

                } 


                this.getUnitScale = function(){
                    return thisscale.unitscale;
                }

                this.getUnit = function(){

                         var uname = 'Metric';
                
                         switch (this.Unitofmeasure) {
                            case 1:
                                uname = 'Metric';
                
                                break;
                            case 2:
                                uname = 'Imperial';
                                break;
                            case 3:
                                uname = 'System';
                                break;
                
                        }
                
                        //1 = Millimeter, 2 = Centimeter, 3 = Decimeter, 4=Meter,5=Kilometer,6=Nautical Miles
                        //1 = Inch,2=Feet,3=Yard,4=Mile,5=Nautical Miles
                    
                        var unitobj = {
                            unit : thisscale.Unitofmeasure,
                            unitname : uname,
                            subunit : thisscale.SubmeasureUnit,
                            label : thisscale.Unitlabel,
                            Arealabel : thisscale.AreaUnitlabel
                        };
                
                        return unitobj;
                

                };


                this.imperialUnit = function(unit){

                    if (unit == 'Inch') {
                        thisscale.SubmeasureUnit = 1;
                    }
                    if (unit == 'Feet') {
                        thisscale.SubmeasureUnit = 2;
                    }
                    if (unit == 'Yard') {
                        thisscale.SubmeasureUnit = 3;
                    }
                    if (unit == 'Mile') {
                        thisscale.SubmeasureUnit = 4;
                    }
                    if (unit == 'Nautical Miles') {
                        thisscale.SubmeasureUnit = 5;
                    }
            
                    switch (thisscale.SubmeasureUnit) {
                        case 1:
                            thisscale.Unitlabel = "in.";
                            thisscale.AreaUnitlabel = "sq.in.";
                            thisscale.unitscale = 1;
                            break;
                        case 2:
                            thisscale.Unitlabel = "ft.";
                            thisscale.AreaUnitlabel = "sq.ft.";
                            thisscale.unitscale = 12;
                            break;
                        case 3:
                            thisscale.Unitlabel = "yd.";
                            thisscale.AreaUnitlabel = "sq.yd.";
                            thisscale.unitscale = 36;
                            break;
                        case 4:
                            thisscale.Unitlabel = "mi.";
                            thisscale.AreaUnitlabel = "sq.mi";
                            thisscale.unitscale = 63360;
                            break;
                        case 5:
                            thisscale.Unitlabel = "nm";
                            thisscale.AreaUnitlabel = "sq.nm";
                            thisscale.unitscale = 72913.3858;
                            break;
            
                    }
                };

                this.metricUnit = function(unit){

                    if (unit == 'Millimeter') {
                        thisscale.SubmeasureUnit = 1;
                    }
                    if (unit == 'Centimeter') {
                        thisscale.SubmeasureUnit = 2;
                    }
                    if (unit == 'Decimeter') {
                        thisscale.SubmeasureUnit = 3;
                    }
                    if (unit == 'Meter') {
                        thisscale.SubmeasureUnit = 4;
                    }
                    if (unit == 'Kilometer') {
                        thisscale.SubmeasureUnit = 5;
                    }
                    if (unit == 'Nautical Miles') {
                        thisscale.SubmeasureUnit = 6;
                    }
            
                    switch (thisscale.SubmeasureUnit) {
                        case 1:
                            thisscale.Unitlabel = "mm";
                            thisscale.AreaUnitlabel = "mm\u00B2";
                            thisscale.unitscale = 1;
                            break;
                        case 2:
                            thisscale.Unitlabel = "cm";
                            thisscale.AreaUnitlabel = "cm\u00B2";
                            thisscale.unitscale = 10;
                            break;
                        case 3:
                            thisscale.Unitlabel = "dm";
                            thisscale.AreaUnitlabel = "dm\u00B2";
                            thisscale.unitscale = 100;
                            break;
                        case 4:
                            thisscale.Unitlabel = "m";
                            thisscale.AreaUnitlabel = "m\u00B2";
                            thisscale.unitscale = 1000;
                            break;
                        case 5:
                            thisscale.Unitlabel = "km";
                            thisscale.AreaUnitlabel = "km\u00B2";
                            thisscale.unitscale = 1000000;
                            break;
                        case 6:
                            thisscale.Unitlabel = "nmi";
                            thisscale.AreaUnitlabel = "nmi\u00B2";
                            thisscale.unitscale = 185200000;
                            break;
            
                    }
                }

                this.setMeasureScaledirect = function (value) {
                    thisscale.measurescale = value;
                };
                this.getMeasureScale = function () {
                    return thisscale.measurescale;
                };
                this.getScaleValue = function () {
                    return thisscale.scaleValue;
                };
                this.setCalibration = function (val) {
                    if (val) {
                        if (nCalibrateSet != 0) {
                            nCalibrateScale = nCalibrateMeasured / nCalibrateSet;
                            nCalibrateScale = 1 / nCalibrateScale;
                            thisscale.measurescale = nCalibrateScale;
                        }
                    }
                    else {
                        nCalibrateScale = 1;
                    }
                    
                    
                    return nCalibrateScale;
                };
                this.setCalibrateScale = function (scale) {
                    thisscale.measurescale = scale;
                };
                this.setMeasureScale = function (scale) {
                    thisscale.scaleValue = scale;
                    var numerator = 0;
                    var denomintaor = 0;
                    if (scale != 'Calibration') {
                        var numarr = scale.split(":");
                        numerator = numarr[0];
                        denomintaor = numarr[1];
                        if (bReverseScale) {
                            thisscale.measurescale = denomintaor / numerator;
                        }
                        else {
                            thisscale.measurescale = numerator / denomintaor;
                        }
                    }
                    else {
                        thisscale.measurescale = nCalibrateScale;
                    }
                }; 
                
                this.setDimPrecision = function(value) {
                    thisscale.ndimprecision = value;
                }

                this.getDimPrecision = function(value) {
                    return thisscale.ndimprecision;
                }

                this.setScaleLabel = function(label) {
                    thisscale.scaleLabel = label;
                }

                this.getScaleLabel = function() {
                    return thisscale.scaleLabel;
                }

                this.resetToDefaultValue = function() {
                    thisscale.measurescale = MeasureScale;
                    thisscale.Unitofmeasure = Unitofmeasure;
                    thisscale.unitname = "Metric";
                    thisscale.SubmeasureUnit = SubmeasureUnit;
                    thisscale.Unitlabel = Unitlabel;
                    thisscale.AreaUnitlabel = AreaUnitlabel;
                    thisscale.unitscale = unitscale;
                    thisscale.scaleValue = "1:1";
                    thisscale.scaleLabel = "1 Millimeter : 1 Millimeter";
                    thisscale.ndimprecision = ndimprecision;
                }

                
            }
        }        

```