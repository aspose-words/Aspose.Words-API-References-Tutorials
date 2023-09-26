---
title: Using Document Ranges in Aspose.Words for Java
linktitle: Using Document Ranges in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 18
url: /java/document-manipulation/using-document-ranges/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        doc.getSections().get(0).getRange().delete();
    }
    @Test
    public void rangesGetText() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        String text = doc.getRange().getText();
```
