---
title: Saving Documents as PCL Format in Aspose.Words for Java
linktitle: Saving Documents as PCL Format in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 21
url: /java/document-loading-and-saving/saving-documents-as-pcl-format/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PclSaveOptions saveOptions = new PclSaveOptions();
        {
            saveOptions.setSaveFormat(SaveFormat.PCL); saveOptions.setRasterizeTransformedElements(false);
        }
        doc.save(getArtifactsDir() + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```
