---
title: Using Sections in Aspose.Words for Java
linktitle: Using Sections in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 23
url: /java/using-document-elements/using-sections/
---

## Complete Source Code
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello1");
        builder.writeln("Hello2");
        Section sectionToAdd = new Section(doc);
        doc.getSections().add(sectionToAdd);
    }
    @Test
    public void deleteSection() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello1");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello2");
        doc.appendChild(new Section(doc));
        doc.getSections().removeAt(0);
    }
    @Test
    public void deleteAllSections() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello1");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello2");
        doc.appendChild(new Section(doc));
        doc.getSections().clear();
    }
    @Test
    public void appendSectionContent() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello1");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello22");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello3");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello45");
        // This is the section that we will append and prepend to.
        Section section = doc.getSections().get(2);
        // This copies the content of the 1st section and inserts it at the beginning of the specified section.
        Section sectionToPrepend = doc.getSections().get(0);
        section.prependContent(sectionToPrepend);
        // This copies the content of the 2nd section and inserts it at the end of the specified section.
        Section sectionToAppend = doc.getSections().get(1);
        section.appendContent(sectionToAppend);
    }
    @Test
    public void cloneSection() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        Section cloneSection = doc.getSections().get(0).deepClone();
    }
    @Test
    public void copySection() throws Exception
    {
        Document srcDoc = new Document(getMyDir() + "Document.docx");
        Document dstDoc = new Document();
        Section sourceSection = srcDoc.getSections().get(0);
        Section newSection = (Section) dstDoc.importNode(sourceSection, true);
        dstDoc.getSections().add(newSection);
        dstDoc.save(getArtifactsDir() + "WorkingWithSection.CopySection.docx");
    }
    @Test
    public void deleteHeaderFooterContent() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        Section section = doc.getSections().get(0);
        section.clearHeadersFooters();
    }
    @Test
    public void deleteSectionContent() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        Section section = doc.getSections().get(0);
        section.clearContent();
    }
    @Test
    public void modifyPageSetupInAllSections() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello1");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello22");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello3");
        doc.appendChild(new Section(doc));
        builder.writeln("Hello45");
        // It is important to understand that a document can contain many sections,
        // and each section has its page setup. In this case, we want to modify them all.
        for (Section section : doc.getSections())
            section.getPageSetup().setPaperSize(PaperSize.LETTER);
        doc.save(getArtifactsDir() + "WorkingWithSection.ModifyPageSetupInAllSections.doc");
    }
    @Test
    public void sectionsAccessByIndex() throws Exception
    {
        Document doc = new Document(getMyDir() + "Document.docx");
        Section section = doc.getSections().get(0);
        section.getPageSetup().setLeftMargin(90.0); // 3.17 cm
        section.getPageSetup().setRightMargin(90.0); // 3.17 cm
        section.getPageSetup().setTopMargin(72.0); // 2.54 cm
        section.getPageSetup().setBottomMargin(72.0); // 2.54 cm
        section.getPageSetup().setHeaderDistance(35.4); // 1.25 cm
        section.getPageSetup().setFooterDistance(35.4); // 1.25 cm
        section.getPageSetup().getTextColumns().setSpacing(35.4); // 1.25 cm
```
