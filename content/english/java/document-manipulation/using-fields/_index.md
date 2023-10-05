---
title: Using Fields in Aspose.Words for Java
linktitle: Using Fields in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Unlock Document Automation with Aspose.Words for Java. Learn how to merge, format, and insert images in Java documents. Comprehensive guide and code examples for efficient document processing.
type: docs
weight: 11
url: /java/document-manipulation/using-fields/
---
 
## Introduction to Using Fields in Aspose.Words for Java

In this step-by-step guide, we'll explore how to use fields in Aspose.Words for Java. Fields are powerful placeholders that can dynamically insert data into your documents. We'll cover various scenarios, including basic field merging, conditional fields, working with images, and alternating row formatting. We'll provide Java code snippets and explanations for each scenario.

## Prerequisites

Before you begin, make sure you have Aspose.Words for Java installed. You can download it from [here](https://releases.aspose.com/words/java/).

## Basic Field Merging

Let's start with a simple field merging example. We have a document template with mail merge fields, and we want to populate them with data. Here's the Java code to achieve this:

```java
Document doc = new Document("Mail merge template.docx");
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
String[] fieldNames = {
    "RecipientName", "SenderName", "FaxNumber", "PhoneNumber",
    "Subject", "Body", "Urgent", "ForReview", "PleaseComment"
};
Object[] fieldValues = {
    "Josh", "Jenny", "123456789", "", "Hello",
    "<b>HTML Body Test message 1</b>", true, false, true
};
doc.getMailMerge().execute(fieldNames, fieldValues);
doc.save("MergedDocument.docx");
```

In this code, we load a document template, set up mail merge fields, and execute the merge. The `HandleMergeField` class handles specific field types such as checkboxes and HTML body content.

## Conditional Fields

You can use conditional fields in your documents. Let's insert an IF field inside our document and populate it with data:

```java
Document doc = new Document("ConditionalFieldTemplate.docx");
FieldIf fieldIf = (FieldIf) doc.getBuilder().insertField(" IF 1 = 2 ");
fieldIf.setResultIfFalse(true);
FieldMergeField mergeField = (FieldMergeField) doc.getBuilder().insertField(" MERGEFIELD FullName ");
DataTable dataTable = new DataTable();
dataTable.getColumns().add("FullName");
dataTable.getRows().add("James Bond");
doc.getMailMerge().execute(dataTable);
```

This code inserts an IF field and a MERGEFIELD inside it. Even though the IF statement is false, we set `setUnconditionalMergeFieldsAndRegions(true)` to count MERGEFIELDs inside false-statement IF fields during the mail merge.

## Working with Images

You can merge images into your documents. Here's an example of merging images from a database into a document:

```java
Document doc = new Document("ImageMergeTemplate.docx");
doc.getMailMerge().setFieldMergingCallback(new HandleMergeImageFieldFromBlob());
String connString = "jdbc:ucanaccess://" + getDatabaseDir() + "Northwind.mdb";
Connection connection = DriverManager.getConnection(connString, "Admin", "");
Statement statement = connection.createStatement();
ResultSet resultSet = statement.executeQuery("SELECT * FROM Employees");
DataTable dataTable = new DataTable(resultSet, "Employees");
doc.getMailMerge().executeWithRegions(dataTable, "Employees");
connection.close();
doc.save("MergedDocumentWithImages.docx");
```

In this code, we load a document template with image merge fields and populate them with images from a database.

## Alternating Row Formatting

You can format alternating rows in a table. Here's how to do it:

```java
Document doc = new Document("AlternatingRowsTemplate.docx");
doc.getMailMerge().setFieldMergingCallback(new HandleMergeFieldAlternatingRows());
DataTable dataTable = getSuppliersDataTable();
doc.getMailMerge().executeWithRegions(dataTable);
doc.save("FormattedDocument.doc");
```

This code formats rows in a table with alternating colors based on the `CompanyName` field.

## Complete Source Code For Using Fields in Aspose.Words for Java

```java
	Document doc = new Document("Your Directory Path" + "Mail merge destinations - Fax.docx");
	// Setup mail merge event handler to do the custom work.
	doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
	// Trim trailing and leading whitespaces mail merge values.
	doc.getMailMerge().setTrimWhitespaces(false);
	String[] fieldNames = {
		"RecipientName", "SenderName", "FaxNumber", "PhoneNumber",
		"Subject", "Body", "Urgent", "ForReview", "PleaseComment"
	};
	Object[] fieldValues = {
		"Josh", "Jenny", "123456789", "", "Hello",
		"<b>HTML Body Test message 1</b>", true, false, true
	};
	doc.getMailMerge().execute(fieldNames, fieldValues);
	doc.save("Your Directory Path" + "WorkingWithFields.MailMergeFormFields.docx");
}
private static class HandleMergeField implements IFieldMergingCallback
{
	/// <summary>
	/// This handler is called for every mail merge field found in the document,
	/// for every record found in the data source.
	/// </summary>
	public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
	{
		if (mBuilder == null)
			mBuilder = new DocumentBuilder(e.getDocument());
		// We decided that we want all boolean values to be output as check box form fields.
		if (e.getFieldValue() instanceof /*boolean*/Boolean)
		{
			// Move the "cursor" to the current merge field.
			mBuilder.moveToMergeField(e.getFieldName());
			String checkBoxName = MessageFormat.format("{0}{1}", e.getFieldName(), e.getRecordIndex());
			mBuilder.insertCheckBox(checkBoxName, (Boolean) e.getFieldValue(), 0);
			return;
		}
		switch (e.getFieldName())
		{
			case "Body":
				mBuilder.moveToMergeField(e.getFieldName());
				mBuilder.insertHtml((String) e.getFieldValue());
				break;
			case "Subject":
			{
				mBuilder.moveToMergeField(e.getFieldName());
				String textInputName = MessageFormat.format("{0}{1}", e.getFieldName(), e.getRecordIndex());
				mBuilder.insertTextInput(textInputName, TextFormFieldType.REGULAR, "", (String) e.getFieldValue(), 0);
				break;
			}
		}
	}
	public void imageFieldMerging(ImageFieldMergingArgs args)
	{
		args.setImageFileName("Image.png");
		args.getImageWidth().setValue(200.0);
		args.setImageHeight(new MergeFieldImageDimension(200.0, MergeFieldImageDimensionUnit.PERCENT));
	}
	private DocumentBuilder mBuilder;
}
@Test
public void mailMergeImageField() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.writeln("{{#foreach example}}");
	builder.writeln("{{Image(126pt;126pt):stempel}}");
	builder.writeln("{{/foreach example}}");
	doc.getMailMerge().setUseNonMergeFields(true);
	doc.getMailMerge().setTrimWhitespaces(true);
	doc.getMailMerge().setUseWholeParagraphAsRegion(false);
	doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS
			| MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS
			| MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS
			| MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);
	doc.getMailMerge().setFieldMergingCallback(new ImageFieldMergingHandler());
	doc.getMailMerge().executeWithRegions(new DataSourceRoot());
	doc.save("Your Directory Path" + "WorkingWithFields.MailMergeImageField.docx");
}
private static class ImageFieldMergingHandler implements IFieldMergingCallback
{
	public void fieldMerging(FieldMergingArgs args)
	{
		//  Implementation is not required.
	}
	public void imageFieldMerging(ImageFieldMergingArgs args) throws Exception
	{
		Shape shape = new Shape(args.getDocument(), ShapeType.IMAGE);
		{
			shape.setWidth(126.0); shape.setHeight(126.0); shape.setWrapType(WrapType.SQUARE);
		}
		shape.getImageData().setImage("Your Directory Path" + "Mail merge image.png");
		args.setShape(shape);
	}
}
public static class DataSourceRoot implements IMailMergeDataSourceRoot
{
	public IMailMergeDataSource getDataSource(String s)
	{
		return new DataSource();
	}
	private static class DataSource implements IMailMergeDataSource
	{
		private boolean next = true;
		private String tableName()
		{
			return "example";
		}
		@Override
		public String getTableName() {
			return tableName();
		}
		public boolean moveNext()
		{
			boolean result = next;
			next = false;
			return result;
		}
		public IMailMergeDataSource getChildDataSource(String s)
		{
			return null;
		}
		public boolean getValue(String fieldName, Ref<Object> fieldValue)
		{
			fieldValue.set(null);
			return false;
		}
	}
}
@Test
public void mailMergeAndConditionalField() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insert a MERGEFIELD nested inside an IF field.
	// Since the IF field statement is false, the result of the inner MERGEFIELD will not be displayed,
	// and the MERGEFIELD will not receive any data during a mail merge.
	FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
	builder.moveTo(fieldIf.getSeparator());
	builder.insertField(" MERGEFIELD  FullName ");
	// We can still count MERGEFIELDs inside false-statement IF fields if we set this flag to true.
	doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
	DataTable dataTable = new DataTable();
	dataTable.getColumns().add("FullName");
	dataTable.getRows().add("James Bond");
	doc.getMailMerge().execute(dataTable);
	// The result will not be visible in the document because the IF field is false,
	// but the inner MERGEFIELD did indeed receive data.
	doc.save("Your Directory Path" + "WorkingWithFields.MailMergeAndConditionalField.docx");
}
@Test
public void mailMergeImageFromBlob() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind employees.docx");
	doc.getMailMerge().setFieldMergingCallback(new HandleMergeImageFieldFromBlob());
	Class.forName("net.ucanaccess.jdbc.UcanaccessDriver");
	String connString = "jdbc:ucanaccess://" + getDatabaseDir() + "Northwind.mdb";
	Connection connection = DriverManager.getConnection(connString, "Admin", "");
	Statement statement = connection.createStatement();
	ResultSet resultSet = statement.executeQuery("SELECT * FROM Employees");
	DataTable dataTable = new DataTable(resultSet, "Employees");
	IDataReader dataReader = new DataTableReader(dataTable);
	doc.getMailMerge().executeWithRegions(dataReader, "Employees");
	connection.close();
	doc.save("Your Directory Path" + "WorkingWithFields.MailMergeImageFromBlob.docx");
}
public static class HandleMergeImageFieldFromBlob implements IFieldMergingCallback
{
	public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs args)
	{
		// Do nothing.
	}
	/// <summary>
	/// This is called when mail merge engine encounters Image:XXX merge field in the document.
	/// You have a chance to return an Image object, file name, or a stream that contains the image.
	/// </summary>
	public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
	{
		// The field value is a byte array, just cast it and create a stream on it.
		ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
		// Now the mail merge engine will retrieve the image from the stream.
		e.setImageStream(imageStream);
	}
}
@Test
public void handleMailMergeSwitches() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Field sample - MERGEFIELD.docx");
	doc.getMailMerge().setFieldMergingCallback(new MailMergeSwitches());
	final String HTML = "<html>\r\n                    <h1>Hello world!</h1>\r\n            </html>";
	doc.getMailMerge().execute(new String[] { "htmlField1" }, new Object[] { HTML });
	doc.save("Your Directory Path" + "WorkingWithFields.HandleMailMergeSwitches.docx");
}
public static class MailMergeSwitches implements IFieldMergingCallback
{
	public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
	{
		if (e.getFieldName().startsWith("HTML"))
		{
			if (e.getField().getFieldCode().contains("\\b"))
			{
				FieldMergeField field = e.getField();
				DocumentBuilder builder = new DocumentBuilder(e.getDocument());
				builder.moveToMergeField(e.getDocumentFieldName(), true, false);
				builder.write(field.getTextBefore());
				builder.insertHtml(e.getFieldValue().toString());
				e.setText("");
			}
		}
	}
	public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs args)
	{
	}
}
@Test
public void alternatingRows() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
	doc.getMailMerge().setFieldMergingCallback(new HandleMergeFieldAlternatingRows());
	DataTable dataTable = getSuppliersDataTable();
	doc.getMailMerge().executeWithRegions(dataTable);
	doc.save("Your Directory Path" + "WorkingWithFields.AlternatingRows.doc");
}
private static class HandleMergeFieldAlternatingRows implements IFieldMergingCallback
{
	/// <summary>
	/// Called for every merge field encountered in the document.
	/// We can either return some data to the mail merge engine or do something else with the document.
	/// In this case we modify cell formatting.
	/// </summary>
	public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
	{
		if (mBuilder == null)
			mBuilder = new DocumentBuilder(e.getDocument());
		if ("CompanyName".equals(e.getFieldName()))
		{
			// Select the color depending on whether the row number is even or odd.
			Color rowColor = isOdd(mRowIdx) 
				? new Color((213), (227), (235)) 
				: new Color((242), (242), (242));
			// There is no way to set cell properties for the whole row at the moment, so we have to iterate over all cells in the row.
			for (int colIdx = 0; colIdx < 4; colIdx++)
			{
				mBuilder.moveToCell(0, mRowIdx, colIdx, 0);
				mBuilder.getCellFormat().getShading().setBackgroundPatternColor(rowColor);
			}
			mRowIdx++;
		}
	}
	public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs args)
	{
		// Do nothing.
	}
	private DocumentBuilder mBuilder;
	private int mRowIdx;
}
/// <summary>
/// Returns true if the value is odd; false if the value is even.
/// </summary>
private static boolean isOdd(int value)
{
	return (value / 2 * 2) == value;
}
/// <summary>
/// Create DataTable and fill it with data.
/// In real life this DataTable should be filled from a database.
/// </summary>
private DataTable getSuppliersDataTable()
{
	DataTable dataTable = new DataTable("Suppliers");
	dataTable.getColumns().add("CompanyName");
	dataTable.getColumns().add("ContactName");
	for (int i = 0; i < 10; i++)
	{
		DataRow datarow = dataTable.newRow();
		dataTable.getRows().add(datarow);
		datarow.set(0, "Company " + i);
		datarow.set(1, "Contact " + i);
	}
	return dataTable;
```

## Conclusion

Aspose.Words for Java provides powerful features for working with fields in your documents. You can perform basic field merging, work with conditional fields, insert images, and format tables with ease. Incorporate these techniques into your document automation processes to create dynamic and customized documents.

## FAQ's

### Can I perform mail merging with Aspose.Words for Java?

Yes, you can perform mail merging in Aspose.Words for Java. You can create document templates with mail merge fields and then populate them with data from various sources. Refer to the provided code examples for details on how to perform mail merging.

### How can I insert images into a document using Aspose.Words for Java?

To insert images into a document, you can use the Aspose.Words for Java library. Refer to the code example in the "Working with Images" section for a step-by-step guide on how to merge images from a database into a document.

### What is the purpose of conditional fields in Aspose.Words for Java?

Conditional fields in Aspose.Words for Java allow you to create dynamic documents by including content conditionally based on certain criteria. In the provided example, an IF field is used to conditionally include data in the document during a mail merge based on the result of the IF statement.

### How can I format alternating rows in a table using Aspose.Words for Java?

To format alternating rows in a table, you can use Aspose.Words for Java to apply specific formatting to rows based on your criteria. In the "Alternating Row Formatting" section, you'll find an example that demonstrates how to format rows with alternating colors based on the `CompanyName` field.

### Where can I find more documentation and resources for Aspose.Words for Java?

You can find comprehensive documentation, code samples, and tutorials for Aspose.Words for Java on the Aspose website: [Aspose.Words for Java Documentation](https://reference.aspose.com/words/java/). This resource will help you explore additional features and functionalities of the library.

### How can I get support or seek help with Aspose.Words for Java?

If you need assistance, have questions, or encounter issues while using Aspose.Words for Java, you can visit the Aspose.Words forum for community support and discussions: [Aspose.Words Forum](https://forum.aspose.com/c/words).

### Is Aspose.Words for Java compatible with different Java IDEs?

Yes, Aspose.Words for Java is compatible with various Java Integrated Development Environments (IDEs) such as Eclipse, IntelliJ IDEA, and NetBeans. You can integrate it into your preferred IDE to streamline your document processing tasks.
