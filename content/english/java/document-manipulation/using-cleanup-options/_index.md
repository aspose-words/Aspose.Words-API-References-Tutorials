---
title: Using Cleanup Options in Aspose.Words for Java
linktitle: Using Cleanup Options in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Enhance Document Clarity with Aspose.Words for Java Cleanup Options. Learn how to remove empty paragraphs, unused regions, and more.
type: docs
weight: 10
url: /java/document-manipulation/using-cleanup-options/
---

## Introduction to Using Cleanup Options in Aspose.Words for Java

In this tutorial, we will explore how to use cleanup options in Aspose.Words for Java to manipulate and clean up documents during the mail merge process. Cleanup options allow you to control various aspects of document cleanup, such as removing empty paragraphs, unused regions, and more.

## Prerequisites

Before we start, make sure you have the Aspose.Words for Java library integrated into your project. You can download it from [here](https://releases.aspose.com/words/java/).

## Step 1: Removing Empty Paragraphs

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert merge fields
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Set cleanup options
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Enable cleanup paragraphs with punctuation marks
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Execute mail merge
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Save the document
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

In this example, we create a new document, insert merge fields, and set the cleanup options to remove empty paragraphs. Additionally, we enable the removal of paragraphs with punctuation marks. After executing the mail merge, the document is saved with the specified cleanup applied.

## Step 2: Removing Unmerged Regions

```java
Document doc = new Document(getMyDir() + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Set cleanup options to remove unused regions
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Execute mail merge with regions
doc.getMailMerge().executeWithRegions(data);

// Save the document
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

In this example, we open an existing document with merge regions, set the cleanup options to remove unused regions, and then execute the mail merge with empty data. This process automatically removes the unused regions from the document.

## Step 3: Removing Empty Fields

```java
Document doc = new Document(getMyDir() + "Table with fields.docx");

// Set cleanup options to remove empty fields
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Execute mail merge
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Save the document
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

In this example, we open a document with merge fields, set the cleanup options to remove empty fields, and execute the mail merge with data. After the merge, any empty fields will be removed from the document.

## Step 4: Removing Unused Fields

```java
Document doc = new Document(getMyDir() + "Table with fields.docx");

// Set cleanup options to remove unused fields
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Execute mail merge
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Save the document
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

In this example, we open a document with merge fields, set the cleanup options to remove unused fields, and execute the mail merge with data. After the merge, any unused fields will be removed from the document.

## Step 5: Removing Containing Fields

```java
Document doc = new Document(getMyDir() + "Table with fields.docx");

// Set cleanup options to remove containing fields
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Execute mail merge
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Save the document
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

In this example, we open a document with merge fields, set the cleanup options to remove containing fields, and execute the mail merge with data. After the merge, the fields themselves will be removed from the document.

## Step 6: Removing Empty Table Rows

```java
Document doc = new Document(getMyDir() + "Table with fields.docx");

// Set cleanup options to remove empty table rows
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Execute mail merge
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Save the document
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

In this example, we open a document with a table and merge fields, set the cleanup options to remove empty table rows, and execute the mail merge with data. After the merge, any empty table rows will be removed from the document.

## Complete Source Code For Using Cleanup Options in Aspose.Words for Java

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

## Conclusion

In this tutorial, you've learned how to use cleanup options in Aspose.Words for Java to manipulate and clean up documents during the mail merge process. These options provide fine-grained control over document cleanup, allowing you to create polished and customized documents with ease.

## FAQ's

### What are cleanup options in Aspose.Words for Java?

Cleanup options in Aspose.Words for Java are settings that allow you to control various aspects of document cleanup during the mail merge process. They enable you to remove unnecessary elements such as empty paragraphs, unused regions, and more, ensuring your final document is well-structured and polished.

### How can I remove empty paragraphs from my document?

To remove empty paragraphs from your document using Aspose.Words for Java, you can set the `MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` option to true. This will automatically eliminate paragraphs that have no content, resulting in a cleaner document.

### What is the purpose of the `REMOVE_UNUSED_REGIONS` cleanup option?

The `MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` option is used to remove regions in a document that have no corresponding data during the mail merge process. It helps keep your document tidy by getting rid of unused placeholders.

### Can I remove empty table rows from a document using Aspose.Words for Java?

Yes, you can remove empty table rows from a document by setting the `MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS` cleanup option to true. This will automatically delete any table rows that do not contain data, ensuring a well-structured table in your document.

### What happens when I set the `REMOVE_CONTAINING_FIELDS` option?

Setting the `MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` option will remove the entire merge field, including its containing paragraph, from the document during the mail merge process. This is useful when you want to eliminate merge fields and their associated text.

### How can I remove unused merge fields from my document?

To remove unused merge fields from a document, you can set the `MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` option to true. This will automatically eliminate merge fields that are not populated during the mail merge, resulting in a cleaner document.

### What is the difference between `REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

The `REMOVE_EMPTY_FIELDS` option removes merge fields that have no data or are empty during the mail merge process. On the other hand, the `REMOVE_UNUSED_FIELDS` option removes merge fields that are not populated with data during the merge. The choice between them depends on whether you want to remove fields with no content or those that are unused in the specific merge operation.

### How can I enable the removal of paragraphs with punctuation marks?

To enable the removal of paragraphs with punctuation marks, you can set the `cleanupParagraphsWithPunctuationMarks` option to true and specify the punctuation marks to be considered for cleanup. This allows you to create a more refined document by removing unnecessary punctuation-only paragraphs.

### Can I customize the cleanup options in Aspose.Words for Java?

Yes, you can customize the cleanup options according to your specific needs. You can choose which cleanup options to apply and configure them as per your document cleanup requirements, ensuring that your final document meets your desired standards.
