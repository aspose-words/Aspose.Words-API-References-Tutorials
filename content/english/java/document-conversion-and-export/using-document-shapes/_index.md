---
title: Using Document Shapes in Aspose.Words for Java
linktitle: Using Document Shapes in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 14
url: /java/document-conversion-and-export/using-document-shapes/
---

## Complete Source Code
```java
        Document doc = new Document();
        doc.ensureMinimum();
        GroupShape groupShape = new GroupShape(doc);
        Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1); { accentBorderShape.setWidth(100.0); accentBorderShape.setHeight(100.0); }
        groupShape.appendChild(accentBorderShape);
        Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
        {
            actionButtonShape.setLeft(100.0); actionButtonShape.setWidth(100.0); actionButtonShape.setHeight(200.0);
        }
        groupShape.appendChild(actionButtonShape);
        groupShape.setWidth(200.0);
        groupShape.setHeight(200.0);
        groupShape.setCoordSize(new Dimension(200, 200));
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.insertNode(groupShape);
        doc.save(getArtifactsDir() + "WorkingWithShapes.AddGroupShape.docx");
    }
    @Test
    public void insertShape() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
            RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);
        shape.setRotation(30.0);
        builder.writeln();
        shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
        shape.setRotation(30.0);
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
        {
            saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
        }
        doc.save(getArtifactsDir() + "WorkingWithShapes.InsertShape.docx", saveOptions);
    }
    @Test
    public void aspectRatioLocked() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
        shape.setAspectRatioLocked(false);
        doc.save(getArtifactsDir() + "WorkingWithShapes.AspectRatioLocked.docx");
    }
    @Test
    public void layoutInCell() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.startTable();
        builder.getRowFormat().setHeight(100.0);
        builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);
        for (int i = 0; i < 31; i++)
        {
            if (i != 0 && i % 7 == 0) builder.endRow();
            builder.insertCell();
            builder.write("Cell contents");
        }
        builder.endTable();
        Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
        {
            watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
            watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
            watermark.isLayoutInCell(true); // Display the shape outside of the table cell if it will be placed into a cell.
            watermark.setWidth(300.0);
            watermark.setHeight(70.0);
            watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
            watermark.setVerticalAlignment(VerticalAlignment.CENTER);
            watermark.setRotation(-40);
        }
        watermark.setFillColor(Color.GRAY);
        watermark.setStrokeColor(Color.GRAY);
        watermark.getTextPath().setText("watermarkText");
        watermark.getTextPath().setFontFamily("Arial");
        watermark.setName("WaterMark_{Guid.NewGuid()}");
        watermark.setWrapType(WrapType.NONE);
        Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
        builder.moveTo(run);
        builder.insertNode(watermark);
        doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
        doc.save(getArtifactsDir() + "WorkingWithShapes.LayoutInCell.docx");
    }
    @Test
    public void addCornersSnipped() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.insertShape(ShapeType.TOP_CORNERS_SNIPPED, 50.0, 50.0);
        OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
        {
            saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
        }
        doc.save(getArtifactsDir() + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
    }
    @Test
    public void getActualShapeBoundsPoints() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
        shape.setAspectRatioLocked(false);
        System.out.println("\nGets the actual bounds of the shape in points: ");
        System.out.println(shape.getShapeRenderer().getBoundsInPoints());
    }
    @Test
    public void verticalAnchor() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Shape textBox = builder.insertShape(ShapeType.TEXT_BOX, 200.0, 200.0);
        textBox.getTextBox().setVerticalAnchor(TextBoxAnchor.BOTTOM);
        builder.moveTo(textBox.getFirstParagraph());
        builder.write("Textbox contents");
        doc.save(getArtifactsDir() + "WorkingWithShapes.VerticalAnchor.docx");
    }
    @Test
    public void detectSmartArtShape() throws Exception
    {
        Document doc = new Document(getMyDir() + "SmartArt.docx");
        List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
        int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
        System.out.println(MessageFormat.format("The document has {0} shapes with SmartArt.", count));
    }
    @Test
    public void updateSmartArtDrawing() throws Exception
    {
        Document doc = new Document(getMyDir() + "SmartArt.docx");
        for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
            if (shape.hasSmartArt())
                shape.updateSmartArtDrawing();
```
