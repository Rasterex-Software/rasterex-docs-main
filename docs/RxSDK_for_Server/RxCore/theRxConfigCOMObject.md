---
title: The RxConfigCOM Object
---

**Component name**: `RxConfigCOM.dll`

## Introduction to RxConfigCOM

### General Information

The `RxLoadSettings` and `RxSaveSettings` objects allow your application to override the default settings used by filters for both file loading and saving.

**NOTE**: `RxConfigCOM` has been designed to cooperate with other RXSDK components and can only be used if these components are utilized to load and display the document.

The C++ listing below demonstrates how the component can be used to configure where the filter should look for AutoCAD font and reference files:

```
CComPtr<IRxLoadSettings> pIRxConfig; // Class member variable
pIRxConfig.CoCreateInstance(CComBSTR("RxConfigCom.RxLoadSettings"));
if (pIRxConfig)
{
    // Setup AutoCAD filter to use fonts, and to load these from a folder named d:\fonts
    pIRxConfig->raw_SetFilterLongValue(rxAcad2kUseFonts, 1);
    pIRxConfig->raw_SetFilterStringValue(rxAcad2kFontFolders, CComBSTR("d:\\fonts"));
    // Setup AutoCAD filter to load external referenced files from two folders:
    pIRxConfig->raw_SetFilterStringValue(rxAcad2kXRefFolders, CComBSTR("d:\\xrefs;d:\\blocks\\xrefs;"));
    // Then tell the engine that we have a configuration object
    CComQIPtr<IDispatch> pDisp = pIRxConfig;
    theApp.m_IRxEngine->raw_SetLoadFilterConfig(pDisp);
}
```

**Note**: It’s critical that the `RxLoadSettings` object pointer is provided to the `RxEngine` object before any file is loaded.

### RxLoadSettings Methods

Contains methods for overriding default values used by filters. This may include XREF paths, font paths, and other settings. For a list of modifiable settings, see the table below.

---

#### SetFilterLongValue

Changes a filter setting that uses a long value. These settings align with those configurable in filter setting dialogs. Each setting is enumerated in the component and can be listed in VB and other development environments. More details are provided in the table below.

##### Syntax

```
SetFilterLongValue(enumLongSettings Setting, long data)
```

##### Parameters

- **Setting**: Enumerated filter setting.
- **data**: The long value to set.

##### Returns

- `HRESULT`: `S_OK` on success, `E_FAIL` on failure.

---

##### Available Enumerated Long Values

| Name                         | Filter                  | Effect                                                                                                            |
| ---------------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------- |
| rxAcad2kAllowBigFontFix      | RxFilter_ACAD           | If non-zero, enables big font fix for mixed codepages; 0 disables it.                                             |
| rxAcad2kDefaultLayerSettings | RxFilter_ACAD           | If non-zero, uses default layer states.                                                                           |
| rxAcad2kEnableRasterColor    | RxFilter_ACAD           | If non-zero, the defined draw color in the DWG file should be used for monochrome image.                          |
| rxAcad2kHideFrozenLayer      | RxFilter_ACAD           | Frozen layers will be hidden if non-zero.                                                                         |
| rxAcad2kLoadAcis             | RxFilter_ACAD           | ACIS solid (3D objects) will be loaded if non-zero.                                                               |
| rxAcad2kLoadAttributes       | RxFilter_ACAD           | Blocks and block attributes will be loaded if non-zero.                                                           |
| rxAcad2kLoadXADATA           | RxFilter_ACAD           | If non-zero, the filter will load XDATA for applications defined by `rxAcad2kXDATAApps`.                          |
| rxAcad2kUseDefaultFont       | RxFilter_ACAD           | If non-zero, uses a user-defined font for missing fonts. See `rxAcadDefaultFont`.                                 |
| rxAcad2kUseFonts             | RxFilter_ACAD           | If non-zero, searches for AutoCAD fonts and uses them; otherwise, uses an internal font. See `rxAcadFontFolders`. |
| rxAcad2kZoomResolution       | RxFilter_ACAD           | Increases resolution in vectorized AutoCAD files (legal values: 1 to 10).                                         |
| rxBinaryPaperSize            | RxFilter_Binary         | Sets paper size for listing binary files.                                                                         |
| rxBinaryPrinterDefaults      | RxFilter_Binary         | If non-zero, uses the default printer's paper size for listing binary files.                                      |
| rxCalcompAutoDetect          | RxFilter_Calcomp        | If non-zero, attempts to auto-detect files.                                                                       |
| rxCalcompEOB                 | RxFilter_Calcomp        | Calcomp end-of-block byte.                                                                                        |
| rxCalcompExtraSync           | RxFilter_Calcomp        | Calcomp extra sync byte. See `rxCalcompUseExtraSync`.                                                             |
| rxCalcompSync                | RxFilter_Calcomp        | Calcomp sync byte.                                                                                                |
| rxCalcompUseCheckSum         | RxFilter_Calcomp        | If non-zero, assumes Calcomp files use a checksum.                                                                |
| rxCalcompUseExtraSync        | RxFilter_Calcomp        | If non-zero, assumes Calcomp files use an extra sync byte.                                                        |
| rxDgn8RecalcExtents          | RxFilter_MicrostationV8 | If non-zero, calculates the drawing extent before loading.                                                        |
| rxDgn8RenderDeviation        | RxFilter_MicrostationV8 | Set render deviation to use for loaded DGN files. Values from 0 to 3 is valid. Value 0 is the lowest resolution.  |
| rxGerberIncremental          | RxFilter_Gerber         | If non-zero, assumes Gerber RS-274D files use incremental coordinates.                                                    |
| rxGerberFileUnits            | RxFilter_Gerber         | Sets Gerber RS-274D file units: `1/100 mm`, `1/1000 inch`, `1/10000 inch`, `1/100000 inch`, `1/1000000 inch`              |
| rxMe10CompatibleMode         | RxFilter_ME10           | Enables support for older ME10 files if non-zero.                                                                 |
| rxMe10LoadParts              | RxFilter_ME10           | If non-zero, all parts will be loaded as separate blocks for listing.                                             |
| rxMe10LoadAllParts           | RxFilter_ME10           | If non-zero, all instances of all parts will be loaded.                                                           |
| rxPDFLoadBookmarks           | RxFilter_DynaPDF        | If non-zero, bookmarks in PDF files will be loaded.                                                               |
| rxPDFLoadLayers              | RxFilter_DynaPDF        | If non-zero, layers in PDF files will be loaded.                                                                  |
| rxPDFLoadLinks               | RxFilter_DynaPDF        | If non-zero, links in PDF files will be loaded.                                                                   |
| rxTextFontCharSet            | RxFilter_Text           | Character set for text font (see `LOGFONT` in Platform SDK).                                                      |
| rxTextFontHeight             | RxFilter_Text           | Height for text font (see `LOGFONT` in Platform SDK).                                                             |
| rxTextFontItalic             | RxFilter_Text           | If non-zero, text filter font will be italic.                                                                     |
| rxTextFontWeight             | RxFilter_Text           | Weight for text font (e.g., `FW_BOLD`, `FW_EXTRABOLD`; see `LOGFONT` in Platform SDK).                            |
| rxTextPaperSize              | RxFilter_Text           | Sets paper size for listing text files.                                                                           |
| rxTextPrinterDefaults        | RxFilter_Text           | If non-zero, uses the default printer's paper size.                                                               |
| rxTextWordWrap               | RxFilter_Text           | If non-zero, enables word wrapping.                                                                               |

---

#### SetFilterStringValue

Changes a filter setting that uses a string value. Each setting is enumerated in the component and can be listed in VB and other development environments.

##### Syntax

```
SetFilterStringValue(enumStringSettings Setting, BSTR data)
```

##### Parameters

- **Setting**: Enumerated filter setting.
- **data**: The string value to set.

##### Returns

- `HRESULT`: `S_OK` on success, `E_FAIL` on failure.

---

##### Available Enumerated String Values

| Name                                   | Filter                          | Effect                                                                                                                     |
| -------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| rxAcad2kDefaultFont                    | RxFilter_ACAD                   | If `rxAcadUseDefaultFont` is non-zero, specifies the default font file for missing fonts or to override the internal font. |
| rxAcad2kFontFolders                    | RxFilter_ACAD                   | Set one or more folders (separated by `;`) to search for requested fonts.                                                  |
| rxAcad2kXDATAApps                      | RxFilter_ACAD                   | Set one or more application names (separated by `;`) for which the filter will load XDATA, if rxAcad2kLoadXDATA is set to non-zero. | 
| rxAcad2kXRefFolders                    | RxFilter_ACAD                   | Sets one or more folders (separated by `;`) that will be searched for requested reference files.                                       |
| rxBinaryFontName                       | RxFilter_Binary                 | Name of the font to be used when loading binary files.                                                                     |
| rxDgn8FontResourceFile                 | RxFilter_MicrostationV8         | Sets the full path of a MicroStation font resource file to use during file load.                                           |
| rxDgn8ReferenceFolders                 | RxFilter_MicrostationV8         | Sets one or more folders (separated by `;`) to search for requested reference files.                                       |
| rxDgn8ShxFontFolders                   | RxFilter_MicrostationV8         | Sets one or more folders (separated by `;`) to search for requested SHX font files.                                        |
| rxPDFPassword                          | RxFilter_DynaPDF                | Set password to be used when loading password protected PDF files.                                                                  |
| rxTextFontName                         | RxFilter_Text                   | Name of the font used for displaying text files.                                                                           |
| rxVC5FontFolder                        | RxFilter_VC5                    | Sets a folder to search for any requested SHX font files.                                                                      |

---

### RxSaveSettings Methods

---

#### SetFilterLongValue

Changes a filter setting that uses a long value for saving. These settings align with those configurable in filter save setting dialogs. Each setting is enumerated in the component and can be listed in VB and other development environments. More details are provided in the table below.

##### Syntax

```
SetFilterLongValue(enumLongSettings Setting, long data)
```

##### Parameters

- **Setting**: Enumerated filter setting.
- **data**: The long value to set.

##### Returns

- `HRESULT`: `S_OK` on success, `E_FAIL` on failure.

---

##### Available Enumerated Long Values

| Name                               | Filter        | Effect                                                                                                                                                                                                                                          |
| ---------------------------------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rxAcadDwgVersion                   | RxFilter_ACAD | Set the destination format for DWG conversions: 0: `AutoCAD R12`, 1: `AutoCAD R13`, 2: `AutoCAD R14`, 3: `AutoCAD 2000`, 4: `AutoCAD 2004`, 5: `AutoCAD 2007`, 6: `AutoCAD 2010`, 7: `AutoCAD 2013`, 8: `AutoCAD 2018`. |
| rxAcadDxfVersion                   | RxFilter_ACAD | Set the destination format for DXF conversions: 0: `AutoCAD R12`, 1: `AutoCAD R13`, 2: `AutoCAD R14`, 3: `AutoCAD 2000`, 4: `AutoCAD 2004`, 5: `AutoCAD 2007`, 6: `AutoCAD 2010`, 7: `AutoCAD 2013`, 8: `AutoCAD 2018`. |
| rxAcadDxfFormat                    | RxFilter_ACAD | Set DXF file format type: 0: `ASCII`, 1: `Binary`.                                                                                                                                                                                             |
| RxPDFComments                      | RxFilter_PDFW | If non-zero, convert Rasterex markup elements to native PDF comments/annotations.                                                                                                                                                               |
| RxPDFDrawMode                      | RxFilter_PDFW | If non-zero, enables layer support for draw modes in converted PDF files (includes transparent objects).                                                                                                                                        |
| RxPDFLayer                         | RxFilter_PDFW | If non-zero, enables layer support in converted PDF files.                                                                                                                                                                                      |
| rxPDFMonoCompression               | RxFilter_PDWF | Set compression method to be used for monochrome images added to converted PDF files: 0: `Inflate`, 1: `JBIG`.                                                                                                                                  |
| rxPDFStandardSelect                | RxFilter_PDFW | Select PDF standard for conversion: 0: `Plain PDF`, 1: `PDF/A-1b`, 2: `PDF/A-2b`, 3: `PDF/A-3b`, 4: `PDF/A-2u`, 5: `PDF/A-3u`, 6: `PDF/A-4`, 7: `PDF/A-4e`.                                                                                     |
| rxTiffColorCompression             | RxFilter_TIFF | Sets compression method for TIFF color images: 0: `Uncompressed`, 1: `Packbits`, 2: `LZW`.                                                                                                                                                      |
| rxTiffMonoCompression              | RxFilter_TIFF | Sets compression method for TIFF monochrome images: 0: `Uncompressed`, 1: `CCITT Group 3`, 2: `CCITT Group 4`, 3: `Packbits`, 4: `LZW`.                                                                                                         |
| rxTiffByteOrder                    | RxFilter_TIFF | Sets byte ordering in converted TIFF images: 0: `Motorola (Big-Endian)`, 1: `Intel (Little-Endian)`.                                                                                                                                            |
