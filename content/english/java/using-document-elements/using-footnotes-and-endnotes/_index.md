---
title: Using Footnotes and Endnotes in Aspose.Words for Java
linktitle: Using Footnotes and Endnotes in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 13
url: /java/using-document-elements/using-footnotes-and-endnotes/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Document.docx");
        // Specify the number of columns with which the footnotes area is formatted.
        doc.getFootnoteOptions().setColumns(3);
        doc.save(getArtifactsDir() + "WorkingWithFootnotes.SetFootNoteColumns.docx");
    }
    @Test
    public void setFootnoteAndEndNotePosition() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
        doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(getArtifactsDir() + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
    }
    @Test
    public void setEndnoteOptions() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Some text");
        builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
        EndnoteOptions option = doc.getEndnoteOptions();
        option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
        option.setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(getArtifactsDir() + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```
