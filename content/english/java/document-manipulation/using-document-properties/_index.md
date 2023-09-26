---
title: Using Document Properties in Aspose.Words for Java
linktitle: Using Document Properties in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 32
url: /java/document-manipulation/using-document-properties/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        String variables = "";
        for (Map.Entry<String, String> entry : doc.getVariables())
        {
            String name = entry.getKey();
            String value = entry.getValue();
            if ("".equals(variables))
            {
                variables = "Name: " + name + "," + "Value: {1}" + value;
            }
            else
            {
                variables = variables + "Name: " + name + "," + "Value: {1}" + value;
            }
        }
        System.out.println("\nDocument have following variables " + variables);
    }
    @Test
    public void enumerateProperties() throws Exception
    {
        Document doc = new Document(getMyDir() + "Properties.docx");
        System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
        System.out.println("2. Built-in Properties");
        for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
            System.out.println(MessageFormat.format("{0} : {1}",prop.getName(),prop.getValue()));
        System.out.println("3. Custom Properties");
        for (DocumentProperty prop : doc.getCustomDocumentProperties())
            System.out.println(MessageFormat.format("{0} : {1}",prop.getName(),prop.getValue()));
    }
    @Test
    public void addCustomDocumentProperties() throws Exception
    {
        Document doc = new Document(getMyDir() + "Properties.docx");
        CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();
        if (customDocumentProperties.get("Authorized") != null) return;
        customDocumentProperties.add("Authorized", true);
        customDocumentProperties.add("Authorized By", "John Smith");
        customDocumentProperties.add("Authorized Date", new Date());
        customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
        customDocumentProperties.add("Authorized Amount", 123.45);
    }
    @Test
    public void removeCustomDocumentProperties() throws Exception
    {
        Document doc = new Document(getMyDir() + "Properties.docx");
        doc.getCustomDocumentProperties().remove("Authorized Date");
    }
    @Test
    public void removePersonalInformation() throws Exception
    {
        Document doc = new Document(getMyDir() + "Properties.docx"); { doc.setRemovePersonalInformation(true); }
        doc.save(getArtifactsDir() + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
    }
    @Test
    public void configuringLinkToContent() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.startBookmark("MyBookmark");
        builder.writeln("Text inside a bookmark.");
        builder.endBookmark("MyBookmark");
        // Retrieve a list of all custom document properties from the file.
        CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();
        // Add linked to content property.
        DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
        customProperty = customProperties.get("Bookmark");
        boolean isLinkedToContent = customProperty.isLinkToContent();
        String linkSource = customProperty.getLinkSource();
        String customPropertyValue = customProperty.getValue().toString();
    }
    @Test
    public void convertBetweenMeasurementUnits() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        PageSetup pageSetup = builder.getPageSetup();
        pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
        pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
        pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
        pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
        pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
        pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
    }
    @Test
    public void useControlCharacters()
    {
        final String TEXT = "test\r";
        // Replace "\r" control character with "\r\n".
        String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
```
