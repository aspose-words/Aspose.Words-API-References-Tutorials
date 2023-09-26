---
title: Formatting Documents in Aspose.Words for Java
linktitle: Formatting Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 29
url: /java/document-manipulation/formatting-documents/
---

## Complete Source Code
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        ParagraphFormat paragraphFormat = builder.getParagraphFormat();
        paragraphFormat.setAddSpaceBetweenFarEastAndAlpha(true);
        paragraphFormat.setAddSpaceBetweenFarEastAndDigit(true);
        builder.writeln("Automatically adjust space between Asian and Latin text");
        builder.writeln("Automatically adjust space between Asian text and numbers");
        doc.save(getArtifactsDir() + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
    }
    @Test
    public void asianTypographyLineBreakGroup() throws Exception
    {
        Document doc = new Document(getMyDir() + "Asian typography.docx");
        ParagraphFormat format = doc.getFirstSection().getBody().getParagraphs().get(0).getParagraphFormat();
        format.setFarEastLineBreakControl(false);
        format.setWordWrap(true);
        format.setHangingPunctuation(false);
        doc.save(getArtifactsDir() + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
    }
    @Test
    public void paragraphFormatting() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        ParagraphFormat paragraphFormat = builder.getParagraphFormat();
        paragraphFormat.setAlignment(ParagraphAlignment.CENTER);
        paragraphFormat.setLeftIndent(50.0);
        paragraphFormat.setRightIndent(50.0);
        paragraphFormat.setSpaceAfter(25.0);
        builder.writeln(
            "I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
        builder.writeln(
            "I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");
        doc.save(getArtifactsDir() + "DocumentFormatting.ParagraphFormatting.docx");
    }
    @Test
    public void multilevelListFormatting() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2.1");
        builder.writeln("Item 2.2");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2.2.1");
        builder.writeln("Item 2.2.2");
        builder.getListFormat().listOutdent();
        builder.writeln("Item 2.3");
        builder.getListFormat().listOutdent();
        builder.writeln("Item 3");
        builder.getListFormat().removeNumbers();
        doc.save(getArtifactsDir() + "DocumentFormatting.MultilevelListFormatting.docx");
    }
    @Test
    public void applyParagraphStyle() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.TITLE);
        builder.write("Hello");
        doc.save(getArtifactsDir() + "DocumentFormatting.ApplyParagraphStyle.docx");
    }
    @Test
    public void applyBordersAndShadingToParagraph() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        BorderCollection borders = builder.getParagraphFormat().getBorders();
        borders.setDistanceFromText(20.0);
        borders.getByBorderType(BorderType.LEFT).setLineStyle(LineStyle.DOUBLE);
        borders.getByBorderType(BorderType.RIGHT).setLineStyle(LineStyle.DOUBLE);
        borders.getByBorderType(BorderType.TOP).setLineStyle(LineStyle.DOUBLE);
        borders.getByBorderType(BorderType.BOTTOM).setLineStyle(LineStyle.DOUBLE);
        Shading shading = builder.getParagraphFormat().getShading();
        shading.setTexture(TextureIndex.TEXTURE_DIAGONAL_CROSS);
        shading.setBackgroundPatternColor(Color.lightGray);
        shading.setForegroundPatternColor(Color.orange);
        builder.write("I'm a formatted paragraph with double border and nice shading.");
        doc.save(getArtifactsDir() + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
    }
    @Test
    public void changeAsianParagraphSpacingAndIndents() throws Exception
    {
        Document doc = new Document(getMyDir() + "Asian typography.docx");
        ParagraphFormat format = doc.getFirstSection().getBody().getFirstParagraph().getParagraphFormat();
        format.setCharacterUnitLeftIndent(10.0);       // ParagraphFormat.LeftIndent will be updated
        format.setCharacterUnitRightIndent(10.0);      // ParagraphFormat.RightIndent will be updated
        format.setCharacterUnitFirstLineIndent(20.0);  // ParagraphFormat.FirstLineIndent will be updated
        format.setLineUnitBefore(5.0);                 // ParagraphFormat.SpaceBefore will be updated
        format.setLineUnitAfter(10.0);                 // ParagraphFormat.SpaceAfter will be updated
        doc.save(getArtifactsDir() + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
    }
    @Test
    public void snapToGrid() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Optimize the layout when typing in Asian characters.
        Paragraph par = doc.getFirstSection().getBody().getFirstParagraph();
        par.getParagraphFormat().setSnapToGrid(true);
        builder.writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
                        "tempor incididunt ut labore et dolore magna aliqua.");
        par.getRuns().get(0).getFont().setSnapToGrid(true);
        doc.save(getArtifactsDir() + "Paragraph.SnapToGrid.docx");
    }
    @Test
    public void getParagraphStyleSeparator() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        for (Paragraph paragraph : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
        {
            if (paragraph.getBreakIsStyleSeparator())
            {
                System.out.println("Separator Found!");
            }
        }
```
