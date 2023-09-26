---
title: Using OLE Objects and ActiveX Controls in Aspose.Words for Java
linktitle: Using OLE Objects and ActiveX Controls in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 21
url: /java/using-document-elements/using-ole-objects-and-activex/
---

## Complete Source Code
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.insertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
        doc.save(getArtifactsDir() + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
    }
    @Test
    public void insertOleObjectWithOlePackage() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        byte[] bs = FileUtils.readFileToByteArray(new File(getMyDir() + "Zip file.zip"));
        try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
        {
            Shape shape = builder.insertOleObject(stream, "Package", true, null);
            OlePackage olePackage = shape.getOleFormat().getOlePackage();
            olePackage.setFileName("filename.zip");
            olePackage.setDisplayName("displayname.zip");
            doc.save(getArtifactsDir() + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
        }
        Shape oleShape = (Shape) doc.getChild(NodeType.SHAPE, 0, true);
        byte[] oleRawData = oleShape.getOleFormat().getRawData();
    }
    @Test
    public void insertOleObjectAsIcon() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.insertOleObjectAsIcon(getMyDir() + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico",
            "My embedded file");
        doc.save(getArtifactsDir() + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
    }
    @Test
    public void insertOleObjectAsIconUsingStream() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        try(ByteArrayInputStream stream = new ByteArrayInputStream(FileUtils.readFileToByteArray(new File(getMyDir() + "Presentation.pptx"))))
    	{
            builder.insertOleObjectAsIcon(stream, "Package", getImagesDir() + "Logo icon.ico", "My embedded file");
    	}
        doc.save(getArtifactsDir() + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
    }
    @Test
    public void readActiveXControlProperties() throws Exception
    {
        Document doc = new Document(getMyDir() + "ActiveX controls.docx");
        String properties = "";
        for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
        {
            if (shape.getOleFormat() == null) break;
            OleControl oleControl = shape.getOleFormat().getOleControl();
            if (oleControl.isForms2OleControl())
            {
                Forms2OleControl checkBox = (Forms2OleControl) oleControl;
                properties = properties + "\nCaption: " + checkBox.getCaption();
                properties = properties + "\nValue: " + checkBox.getValue();
                properties = properties + "\nEnabled: " + checkBox.getEnabled();
                properties = properties + "\nType: " + checkBox.getType();
                if (checkBox.getChildNodes() != null)
                {
                    properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
                }
                properties += "\n";
            }
        }
        properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
        System.out.println("\n" + properties);
```
