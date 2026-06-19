---
title: Pre-Converting Content 
---

# Pre-Converting Files

Rasterex content can be generated independently of the Web Viewer.

This allows applications to prepare document content in advance using the Rasterex REST API. Once content has been generated, files can later be opened in the Rasterex Web Viewer without requiring on-demand processing.

Typical use cases include:

- Document management systems
- Engineering repositories
- Construction project portals
- Scheduled batch processing
- Archive and migration workflows

## Overview

The pre-conversion workflow consists of two separate steps:

```text
Application
     │
     ▼
REST API GetFile
     │
     ▼
Content Generated
     │
     ▼
Ready For Viewing
```

The Web Viewer is not required during the content generation phase.

## Pre-Conversion Request

The following example submits a file to the Rasterex server for processing.

```javascript
async function preConvertRasterex(
  urlFilename,
  cacheID,
  displayName,
  mime
) {
  const xmlPayload = `<?xml version="1.0" encoding="UTF-8"?>
<RxViewServer>
<Command>GetFile</Command>
<LicenseID>1</LicenseID>
<FileURL>${escapeXml(urlFilename)}</FileURL>
<CacheID>${escapeXml(cacheID)}</CacheID>
<DisplayName>${escapeXml(displayName)}</DisplayName>
<Mime>${escapeXml(mime)}</Mime>
</RxViewServer>`;

  const response = await fetch(
    "https://yourserver/RxBinWeb/RxCSISAPI.dll?WebClientPublish",
    {
      method: "POST",
      headers: {
        "Content-Type": "application/xml"
      },
      body: xmlPayload
    }
  );

  if (!response.ok) {
    throw new Error(
      `Pre-conversion failed: ${response.status}`
    );
  }

  return await response.text();
}
```

## Example

```javascript
await preConvertRasterex(
  "https://example.com/files/drawing.dwg",
  "drawing-001",
  "Drawing A1",
  "application/dwg"
);
```

After the request completes, content is available on the Rasterex server and the file is ready for viewing.

## Opening the File

Once content has been generated, the file can be opened normally using the Web Viewer.

```javascript
const fileObject = {
  filepath: "https://example.com/files/drawing.dwg",
  cacheid: "drawing-001",
  displayname: "Drawing A1",
  mime: "application/dwg"
};

RxCore.openFile(fileObject);
```

## Live Demonstration

A complete working example is available here:

https://test.rasterex.com/preconvert.html

The demonstration performs the following steps:

1. Creates a batch of files.
2. Submits each file for pre-conversion.
3. Tracks processing status.
4. Marks files as ready when content generation completes.
5. Opens ready files in the Rasterex Web Viewer.

## Notes

### Cache IDs

Each file must be assigned a unique Cache ID. The Cache ID is later used when opening the file in the viewer.

## Source Files

The source files can be URLs or a server-side file reference.  
If using a URL, make sure the content is available with the correct MIME types on the source server.