---
title: Using Document Options and Settings in Aspose.Words for Java
linktitle: Using Document Options and Settings in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Unlock the Power of Aspose.Words for Java. Master Document Options and Settings for Seamless Document Management. Optimize, Customize, and More.
type: docs
weight: 31
url: /java/document-manipulation/using-document-options-and-settings/
---

## Introduction to Using Document Options and Settings in Aspose.Words for Java

In this comprehensive guide, we will explore how to leverage the powerful features of Aspose.Words for Java to work with document options and settings. Whether you're a seasoned developer or just getting started, you'll find valuable insights and practical examples to enhance your document processing tasks.

## Optimizing Documents for Compatibility

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
```

One key aspect of document management is ensuring compatibility with different versions of Microsoft Word. Aspose.Words for Java provides a straightforward way to optimize documents for specific Word versions. In the above example, we optimize a document for Word 2016, ensuring seamless compatibility.

## Identifying Grammatical and Spelling Errors

```java
@Test
public void showGrammaticalAndSpellingErrors() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    doc.setShowGrammaticalErrors(true);
    doc.setShowSpellingErrors(true);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
}
```

Accuracy is paramount when dealing with documents. Aspose.Words for Java enables you to highlight grammatical and spelling errors within your documents, making proofreading and editing more efficient.

## Cleaning Up Unused Styles and Lists

```java
@Test
public void cleanupUnusedStylesAndLists() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Unused styles.docx");
    // Define cleanup options
    CleanupOptions cleanupOptions = new CleanupOptions();
    cleanupOptions.setUnusedLists(false);
    cleanupOptions.setUnusedStyles(true);
    doc.cleanup(cleanupOptions);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
}
```

Efficiently managing document styles and lists is essential for maintaining document consistency. Aspose.Words for Java allows you to clean up unused styles and lists, ensuring a streamlined and organized document structure.

## Removing Duplicate Styles

```java
@Test
public void cleanupDuplicateStyle() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    // Clean duplicate styles
    CleanupOptions options = new CleanupOptions();
    options.setDuplicateStyle(true);
    doc.cleanup(options);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
}
```

Duplicate styles can lead to confusion and inconsistency in your documents. With Aspose.Words for Java, you can easily remove duplicate styles, maintaining document clarity and coherence.

## Customizing Document Viewing Options

```java
@Test
public void viewOptions() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    // Customize viewing options
    doc.getViewOptions().setViewType(ViewType.PAGE_LAYOUT);
    doc.getViewOptions().setZoomPercent(50);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
}
```

Tailoring the viewing experience of your documents is crucial. Aspose.Words for Java allows you to set various viewing options, such as page layout and zoom percentage, to enhance document readability.

## Configuring Document Page Setup

```java
@Test
public void documentPageSetup() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    // Configure page setup options
    doc.getFirstSection().getPageSetup().setLayoutMode(SectionLayoutMode.GRID);
    doc.getFirstSection().getPageSetup().setCharactersPerLine(30);
    doc.getFirstSection().getPageSetup().setLinesPerPage(10);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
}
```

Precise page setup is crucial for document formatting. Aspose.Words for Java empowers you to set layout modes, characters per line, and lines per page, ensuring your documents are visually appealing.

## Setting Editing Languages

```java
@Test
public void addJapaneseAsEditingLanguages() throws Exception
{
    LoadOptions loadOptions = new LoadOptions();
    // Set language preferences for editing
    loadOptions.getLanguagePreferences().addEditingLanguage(EditingLanguage.JAPANESE);
    Document doc = new Document("Your Directory Path" + "No default editing language.docx", loadOptions);
    // Check the overridden editing language
    int localeIdFarEast = doc.getStyles().getDefaultFont().getLocaleIdFarEast();
    System.out.println(localeIdFarEast == (int) EditingLanguage.JAPANESE
            ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
            : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
}
```

Editing languages play a vital role in document processing. With Aspose.Words for Java, you can set and customize editing languages to suit your document's linguistic needs.

## Complete Source Code For Using Document Options and Settings in Aspose.Words for Java

```java
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
}
@Test
public void showGrammaticalAndSpellingErrors() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.setShowGrammaticalErrors(true);
	doc.setShowSpellingErrors(true);
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
}
@Test
public void cleanupUnusedStylesAndLists() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Unused styles.docx");
	// Combined with the built-in styles, the document now has eight styles.
	// A custom style is marked as "used" while there is any text within the document
	// formatted in that style. This means that the 4 styles we added are currently unused.
	System.out.println(MessageFormat.format("Count of styles before Cleanup: {0}\n", doc.getStyles().getCount()) +
						  MessageFormat.format("Count of lists before Cleanup: {0}", doc.getLists().getCount()));
	// Cleans unused styles and lists from the document depending on given CleanupOptions. 
	CleanupOptions cleanupOptions = new CleanupOptions(); { cleanupOptions.setUnusedLists(false); cleanupOptions.setUnusedStyles(true); }
	doc.cleanup(cleanupOptions);
	System.out.println(MessageFormat.format("Count of styles after Cleanup was decreased: {0}\n", doc.getStyles().getCount()) +
						  MessageFormat.format("Count of lists after Cleanup is the same: {0}", doc.getLists().getCount()));
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
}
@Test
public void cleanupDuplicateStyle() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	// Count of styles before Cleanup.
	System.out.println(doc.getStyles().getCount());
	// Cleans duplicate styles from the document.
	CleanupOptions options = new CleanupOptions(); { options.setDuplicateStyle(true); }
	doc.cleanup(options);
	// Count of styles after Cleanup was decreased.
	System.out.println(doc.getStyles().getCount());
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
}
@Test
public void viewOptions() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getViewOptions().setViewType(ViewType.PAGE_LAYOUT);
	doc.getViewOptions().setZoomPercent(50);
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
}
@Test
public void documentPageSetup() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	// Set the layout mode for a section allowing to define the document grid behavior.
	// Note that the Document Grid tab becomes visible in the Page Setup dialog of MS Word
	// if any Asian language is defined as editing language.
	doc.getFirstSection().getPageSetup().setLayoutMode(SectionLayoutMode.GRID);
	doc.getFirstSection().getPageSetup().setCharactersPerLine(30);
	doc.getFirstSection().getPageSetup().setLinesPerPage(10);
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
}
@Test
public void addJapaneseAsEditingLanguages() throws Exception
{
	LoadOptions loadOptions = new LoadOptions();
	// Set language preferences that will be used when document is loading.
	loadOptions.getLanguagePreferences().addEditingLanguage(EditingLanguage.JAPANESE);
	Document doc = new Document("Your Directory Path" + "No default editing language.docx", loadOptions);
	int localeIdFarEast = doc.getStyles().getDefaultFont().getLocaleIdFarEast();
	System.out.println(localeIdFarEast == (int) EditingLanguage.JAPANESE
				? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
				: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
}
@Test
public void setRussianAsDefaultEditingLanguage() throws Exception
{
	LoadOptions loadOptions = new LoadOptions();
	loadOptions.getLanguagePreferences().setDefaultEditingLanguage(EditingLanguage.RUSSIAN);
	Document doc = new Document("Your Directory Path" + "No default editing language.docx", loadOptions);
	int localeId = doc.getStyles().getDefaultFont().getLocaleId();
	System.out.println(localeId == (int) EditingLanguage.RUSSIAN
				? "The document either has no any language set in defaults or it was set to Russian originally."
				: "The document default language was set to another than Russian language originally, so it is not overridden.");
}
@Test
public void setPageSetupAndSectionFormatting() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.getPageSetup().setOrientation(Orientation.LANDSCAPE);
	builder.getPageSetup().setLeftMargin(50.0);
	builder.getPageSetup().setPaperSize(PaperSize.PAPER_10_X_14);
	doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

## Conclusion

In this guide, we've delved into the various document options and settings available in Aspose.Words for Java. From optimization and error display to style cleanup and viewing options, this powerful library offers extensive capabilities for managing and customizing your documents.

## FAQ's

### How do I optimize a document for a specific Word version?

To optimize a document for a specific Word version, use the `optimizeFor` method and specify the desired version. For example, to optimize for Word 2016:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
doc.save("Your Directory Path" + "OptimizedForWord2016.docx");
```

### How can I highlight grammatical and spelling errors in a document?

You can enable the display of grammatical and spelling errors in a document using the following code:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.setShowGrammaticalErrors(true);
doc.setShowSpellingErrors(true);
doc.save("Your Directory Path" + "ShowErrors.docx");
```

### What is the purpose of cleaning up unused styles and lists?

Cleaning up unused styles and lists helps maintain a clean and organized document structure. It removes unnecessary clutter, improving document readability and consistency.

### How can I remove duplicate styles from a document?

To remove duplicate styles from a document, utilize the `cleanup` method with the `duplicateStyle` option set to `true`. Here's an example:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
CleanupOptions options = new CleanupOptions();
options.setDuplicateStyle(true);
doc.cleanup(options);
doc.save("Your Directory Path" + "CleanedDocument.docx");
```

### How do I customize the viewing options for a document?

You can customize document viewing options using the `ViewOptions` class. For example, to set the view type to page layout and zoom to 50%:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.getViewOptions().setViewType(ViewType.PAGE_LAYOUT);
doc.getViewOptions().setZoomPercent(50);
doc.save("Your Directory Path" + "CustomView.docx");
```
