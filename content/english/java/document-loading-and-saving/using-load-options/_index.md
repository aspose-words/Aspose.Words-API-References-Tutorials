---
title: Working with Load Options in Aspose.Words for Java
linktitle: Working with Load Options in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 11
url: /java/document-loading-and-saving/using-load-options/
---

## Complete Source Code
```java
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setUpdateDirtyFields(true);
        }
        Document doc = new Document(getMyDir() + "Dirty field.docx", loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
    }
    @Test
    public void loadEncryptedDocument() throws Exception {
        Document doc = new Document(getMyDir() + "Encrypted.docx", new LoadOptions("docPassword"));
        doc.save(getArtifactsDir() + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
    }
    @Test
    public void convertShapeToOfficeMath() throws Exception {
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setConvertShapeToOfficeMath(true);
        }
        Document doc = new Document(getMyDir() + "Office math.docx", loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
    }
    @Test
    public void setMsWordVersion() throws Exception {
        // Create a new LoadOptions object, which will load documents according to MS Word 2019 specification by default
        // and change the loading version to Microsoft Word 2010.
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setMswVersion(MsWordVersion.WORD_2010);
        }
        Document doc = new Document(getMyDir() + "Document.docx", loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithLoadOptions.SetMsWordVersion.docx");
    }
    @Test
    public void useTempFolder() throws Exception {
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setTempFolder(getArtifactsDir());
        }
        Document doc = new Document(getMyDir() + "Document.docx", loadOptions);
    }
    @Test
    public void warningCallback() throws Exception {
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
        }
        Document doc = new Document(getMyDir() + "Document.docx", loadOptions);
    }
    public static class DocumentLoadingWarningCallback implements IWarningCallback {
        public void warning(WarningInfo info) {
            // Prints warnings and their details as they arise during document loading.
            System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
            System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
        }
    }
    @Test
    public void convertMetafilesToPng() throws Exception {
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setConvertMetafilesToPng(true);
        }
        Document doc = new Document(getMyDir() + "WMF with image.docx", loadOptions);
    }
    @Test
    public void loadChm() throws Exception {
        LoadOptions loadOptions = new LoadOptions();
        {
            loadOptions.setEncoding(Charset.forName("windows-1251"));
        }
        Document doc = new Document(getMyDir() + "HTML help.chm", loadOptions);
```
