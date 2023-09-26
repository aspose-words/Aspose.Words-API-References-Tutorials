---
title: Saving Documents as RTF Format in Aspose.Words for Java
linktitle: Saving Documents as RTF Format in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 23
url: /java/document-loading-and-saving/saving-documents-as-rtf-format/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        RtfSaveOptions saveOptions = new RtfSaveOptions(); { saveOptions.setSaveImagesAsWmf(true); }
        doc.save(getArtifactsDir() + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```
