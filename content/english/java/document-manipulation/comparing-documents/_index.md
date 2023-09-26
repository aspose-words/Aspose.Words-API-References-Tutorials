---
title: Comparing Documents in Aspose.Words for Java
linktitle: Comparing Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 28
url: /java/document-manipulation/comparing-documents/
---

## Complete Source Code
```java
        Document docA = new Document(getMyDir() + "Document.docx");
        Document docB = docA.deepClone();
        // DocA now contains changes as revisions.
        docA.compare(docB, "user", new Date());
        System.out.println(docA.getRevisions().getCount() == 0 ? "Documents are equal" : "Documents are not equal");
    }
    @Test
    public void compareOptions() throws Exception
    {
        Document docA = new Document(getMyDir() + "Document.docx");
        Document docB = docA.deepClone();
        CompareOptions options = new CompareOptions();
        {
            options.setIgnoreFormatting(true);
            options.setIgnoreHeadersAndFooters(true);
            options.setIgnoreCaseChanges(true);
            options.setIgnoreTables(true);
            options.setIgnoreFields(true);
            options.setIgnoreComments(true);
            options.setIgnoreTextboxes(true);
            options.setIgnoreFootnotes(true);
        }
        docA.compare(docB, "user", new Date(), options);
        System.out.println(docA.getRevisions().getCount() == 0 ? "Documents are equal" : "Documents are not equal");
    }
    @Test
    public void comparisonTarget() throws Exception
    {
        Document docA = new Document(getMyDir() + "Document.docx");
        Document docB = docA.deepClone();
        // Relates to Microsoft Word "Show changes in" option in "Compare Documents" dialog box.
        CompareOptions options = new CompareOptions(); { options.setIgnoreFormatting(true); options.setTarget(ComparisonTargetType.NEW); }
        docA.compare(docB, "user", new Date(), options);
    }
    @Test
    public void comparisonGranularity() throws Exception
    {
        DocumentBuilder builderA = new DocumentBuilder(new Document());
        DocumentBuilder builderB = new DocumentBuilder(new Document());
        builderA.writeln("This is A simple word");
        builderB.writeln("This is B simple words");
        CompareOptions compareOptions = new CompareOptions(); { compareOptions.setGranularity(Granularity.CHAR_LEVEL); }
        builderA.getDocument().compare(builderB.getDocument(), "author", new Date(), compareOptions);
```
