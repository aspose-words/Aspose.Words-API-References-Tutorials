---
title: Saving Documents as ODT Format in Aspose.Words for Java
linktitle: Saving Documents as ODT Format in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 19
url: /java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        // Open Office uses centimeters when specifying lengths, widths and other measurable formatting
        // and content properties in documents whereas MS Office uses inches.
        OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
        doc.save(getArtifactsDir() + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```
