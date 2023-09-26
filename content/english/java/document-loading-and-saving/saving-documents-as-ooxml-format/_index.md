---
title: Saving Documents as OOXML Format in Aspose.Words for Java
linktitle: Saving Documents as OOXML Format in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 20
url: /java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
        doc.save(getArtifactsDir() + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
    }
    @Test
    public void ooxmlComplianceIso29500_2008_Strict() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
        doc.save(getArtifactsDir() + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
    }
    @Test
    public void updateLastSavedTimeProperty() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
        doc.save(getArtifactsDir() + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
    }
    @Test
    public void keepLegacyControlChars() throws Exception
    {
        Document doc = new Document(getMyDir() + "Legacy control character.doc");
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
        doc.save(getArtifactsDir() + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
    }
    @Test
    public void setCompressionLevel() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
        doc.save(getArtifactsDir() + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```
