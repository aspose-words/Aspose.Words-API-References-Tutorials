---
title: Using Barcode Generation in Aspose.Words for Java
linktitle: Using Barcode Generation in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 11
url: /java/document-conversion-and-export/using-barcode-generation/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Field sample - BARCODE.docx");
        doc.getFieldOptions().setBarcodeGenerator(new CustomBarcodeGenerator());
        doc.save(getArtifactsDir() + "WorkingWithBarcodeGenerator.GenerateACustomBarCodeImage.pdf");
```
