---
title: Using Structured Document Tags (SDT) in Aspose.Words for Java
linktitle: Using Structured Document Tags (SDT) in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 19
url: /java/document-manipulation/using-structured-document-tags/
---

## Complete Source Code
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
        builder.insertNode(sdtCheckBox);
        doc.save(getArtifactsDir() + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.DOCX);
    }
    @Test
    public void currentStateOfCheckBox() throws Exception
    {
        Document doc = new Document(getMyDir() + "Structured document tags.docx");
        // Get the first content control from the document.
        StructuredDocumentTag sdtCheckBox =
            (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
        if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX)
            sdtCheckBox.setChecked(true);
        doc.save(getArtifactsDir() + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
    }
    @Test
    public void modifyContentControls() throws Exception
    {
        Document doc = new Document(getMyDir() + "Structured document tags.docx");
        for (StructuredDocumentTag sdt : (Iterable<StructuredDocumentTag>) doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG, true))
        {
            switch (sdt.getSdtType())
            {
                case SdtType.PLAIN_TEXT:
                {
                    sdt.removeAllChildren();
                    Paragraph para = (Paragraph) sdt.appendChild(new Paragraph(doc));
                    Run run = new Run(doc, "new text goes here");
                    para.appendChild(run);
                    break;
                }
                case SdtType.DROP_DOWN_LIST:
                {
                    SdtListItem secondItem = sdt.getListItems().get(2);
                    sdt.getListItems().setSelectedValue(secondItem);
                    break;
                }
                case SdtType.PICTURE:
                {
                    Shape shape = (Shape) sdt.getChild(NodeType.SHAPE, 0, true);
                    if (shape.hasImage())
                    {
                        shape.getImageData().setImage(getImagesDir() + "Watermark.png");
                    }
                    break;
                }
            }
        }
        doc.save(getArtifactsDir() + "WorkingWithSdt.ModifyContentControls.docx");
    }
    @Test
    public void comboBoxContentControl() throws Exception
    {
        Document doc = new Document();
        StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
        sdt.getListItems().add(new SdtListItem("Choose an item", "-1"));
        sdt.getListItems().add(new SdtListItem("Item 1", "1"));
        sdt.getListItems().add(new SdtListItem("Item 2", "2"));
        doc.getFirstSection().getBody().appendChild(sdt);
        doc.save(getArtifactsDir() + "WorkingWithSdt.ComboBoxContentControl.docx");
    }
    @Test
    public void richTextBoxContentControl() throws Exception
    {
        Document doc = new Document();
        StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
        Paragraph para = new Paragraph(doc);
        Run run = new Run(doc);
        run.setText("Hello World");
        run.getFont().setColor(Color.GREEN);
        para.getRuns().add(run);
        sdtRichText.getChildNodes().add(para);
        doc.getFirstSection().getBody().appendChild(sdtRichText);
        doc.save(getArtifactsDir() + "WorkingWithSdt.RichTextBoxContentControl.docx");
    }
    @Test
    public void setContentControlColor() throws Exception
    {
        Document doc = new Document(getMyDir() + "Structured document tags.docx");
        StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
        sdt.setColor(Color.RED);
        doc.save(getArtifactsDir() + "WorkingWithSdt.SetContentControlColor.docx");
    }
    @Test
    public void clearContentsControl() throws Exception
    {
        Document doc = new Document(getMyDir() + "Structured document tags.docx");
        StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
        sdt.clear();
        doc.save(getArtifactsDir() + "WorkingWithSdt.ClearContentsControl.doc");
    }
    @Test
    public void bindSdTtoCustomXmlPart() throws Exception
    {
        Document doc = new Document();
        CustomXmlPart xmlPart =
            doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
        StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
        doc.getFirstSection().getBody().appendChild(sdt);
        sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");
        doc.save(getArtifactsDir() + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
    }
    @Test
    public void setContentControlStyle() throws Exception
    {
        Document doc = new Document(getMyDir() + "Structured document tags.docx");
        StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
        Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
        sdt.setStyle(style);
        doc.save(getArtifactsDir() + "WorkingWithSdt.SetContentControlStyle.docx");
    }
    @Test
    public void creatingTableRepeatingSectionMappedToCustomXmlPart() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books",
            "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
            "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
            "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
        Table table = builder.startTable();
        builder.insertCell();
        builder.write("Title");
        builder.insertCell();
        builder.write("Author");
        builder.endRow();
        builder.endTable();
        StructuredDocumentTag repeatingSectionSdt =
            new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
        repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
        table.appendChild(repeatingSectionSdt);
        StructuredDocumentTag repeatingSectionItemSdt = 
            new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
        repeatingSectionSdt.appendChild(repeatingSectionItemSdt);
        Row row = new Row(doc);
        repeatingSectionItemSdt.appendChild(row);
        StructuredDocumentTag titleSdt =
            new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
        titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
        row.appendChild(titleSdt);
        StructuredDocumentTag authorSdt =
            new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
        authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
        row.appendChild(authorSdt);
        doc.save(getArtifactsDir() + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
    }
    @Test
    public void multiSection() throws Exception
    {
        Document doc = new Document(getMyDir() + "Multi-section structured document tags.docx");
        NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);
        for (StructuredDocumentTagRangeStart tag : (Iterable<StructuredDocumentTagRangeStart>) tags)
            System.out.println(tag.getTitle());
    }
    @Test
    public void structuredDocumentTagRangeStartXmlMapping() throws Exception
    {
        Document doc = new Document(getMyDir() + "Multi-section structured document tags.docx");
        // Construct an XML part that contains data and add it to the document's CustomXmlPart collection.
        String xmlPartId = UUID.randomUUID().toString();
        String xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
        CustomXmlPart xmlPart = doc.getCustomXmlParts().add(xmlPartId, xmlPartContent);
        System.out.println(new String(xmlPart.getData(), StandardCharsets.US_ASCII));
        // Create a StructuredDocumentTag that will display the contents of our CustomXmlPart in the document.
        StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, 0, true);
        // If we set a mapping for our StructuredDocumentTag,
        // it will only display a part of the CustomXmlPart that the XPath points to.
        // This XPath will point to the contents second "<text>" element of the first "<root>" element of our CustomXmlPart.
        sdtRangeStart.getXmlMapping().setMapping(xmlPart, "/root[1]/text[2]", null);
        doc.save(getArtifactsDir() + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```
