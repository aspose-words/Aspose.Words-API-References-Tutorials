---
title: Saving Documents in Various Formats with Aspose.Words for Java
linktitle: Saving Documents in Various Formats with Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 14
url: /java/document-loading-and-saving/saving-documents-in-various-formats/
---

## Complete Source Code
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Hello world!");
        DocSaveOptions saveOptions = new DocSaveOptions();
        {
            saveOptions.setPassword("password");
        }
        doc.save(getArtifactsDir() + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
    }
    @Test
    public void doNotCompressSmallMetafiles() throws Exception {
        Document doc = new Document(getMyDir() + "Microsoft equation object.docx");
        DocSaveOptions saveOptions = new DocSaveOptions();
        {
            saveOptions.setAlwaysCompressMetafiles(false);
        }
        doc.save(getArtifactsDir() + "WorkingWithDocSaveOptions.NotCompressSmallMetafiles.docx", saveOptions);
    }
    @Test
    public void doNotSavePictureBullet() throws Exception {
        Document doc = new Document(getMyDir() + "Image bullet points.docx");
        DocSaveOptions saveOptions = new DocSaveOptions();
        {
            saveOptions.setSavePictureBullet(false);
        }
        doc.save(getArtifactsDir() + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```
