---
title: Protecting Documents in Aspose.Words for Java
linktitle: Protecting Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 22
url: /java/document-manipulation/protecting-documents/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        doc.protect(ProtectionType.ALLOW_ONLY_FORM_FIELDS, "password");
    }
    @Test
    public void unprotect() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        doc.unprotect();
    }
    @Test
    public void getProtectionType() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        /*ProtectionType*/int protectionType = doc.getProtectionType();
```
