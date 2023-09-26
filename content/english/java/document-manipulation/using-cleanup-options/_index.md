---
title: Using Cleanup Options in Aspose.Words for Java
linktitle: Using Cleanup Options in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 10
url: /java/document-manipulation/using-cleanup-options/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Mail merge destination - Northwind suppliers.docx");
        DataSet data = new DataSet();
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS |
                                       MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);
        doc.getMailMerge().setMergeDuplicateRegions(true);
        doc.getMailMerge().executeWithRegions(data);
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.RemoveRowsFromTable.docx");
    }
    @Test
    public void cleanupParagraphsWithPunctuationMarks() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
        mergeFieldOption1.setFieldName("Option_1");
        // Here is the complete list of cleanable punctuation marks: ! , . : ; ? ¡ ¿.
        builder.write(" ?  ");
        FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
        mergeFieldOption2.setFieldName("Option_2");
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);
        // The option's default value is true, which means that the behavior was changed to mimic MS Word.
        // If you rely on the old behavior can revert it by setting the option to false.
        doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);
        doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
    }
    @Test
    public void removeUnmergedRegions() throws Exception
    {
        Document doc = new Document(getMyDir() + "Mail merge destination - Northwind suppliers.docx");
        DataSet data = new DataSet();
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);
        // doc.MailMerge.CleanupOptions = MailMergeCleanupOptions.RemoveContainingFields;
        // doc.MailMerge.CleanupOptions |= MailMergeCleanupOptions.RemoveStaticFields;
        // doc.MailMerge.CleanupOptions |= MailMergeCleanupOptions.RemoveEmptyParagraphs;           
        // doc.MailMerge.CleanupOptions |= MailMergeCleanupOptions.RemoveUnusedFields;
        // Merge the data with the document by executing mail merge which will have no effect as there is no data.
        // However the regions found in the document will be removed automatically as they are unused.
        doc.getMailMerge().executeWithRegions(data);
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
    }
    @Test
    public void removeEmptyParagraphs() throws Exception
    {
        Document doc = new Document(getMyDir() + "Table with fields.docx");
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);
        doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
            new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.RemoveEmptyParagraphs.docx");
    }
    @Test
    public void removeUnusedFields() throws Exception
    {
        Document doc = new Document(getMyDir() + "Table with fields.docx");
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);
        doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
            new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.RemoveUnusedFields.docx");
    }
    @Test
    public void removeContainingFields() throws Exception
    {
        Document doc = new Document(getMyDir() + "Table with fields.docx");
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);
        doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
            new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.RemoveContainingFields.docx");
    }
    @Test
    public void removeEmptyTableRows() throws Exception
    {
        Document doc = new Document(getMyDir() + "Table with fields.docx");
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);
        doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
            new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });
        doc.save(getArtifactsDir() + "WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```
