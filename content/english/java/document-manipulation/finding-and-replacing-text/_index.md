---
title: Finding and Replacing Text in Aspose.Words for Java
linktitle: Finding and Replacing Text in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Learn how to find and replace text in Word documents with Aspose.Words for Java. Step-by-step guide with code examples. Enhance your Java document manipulation skills.
type: docs
weight: 15
url: /java/document-manipulation/finding-and-replacing-text/
---

## Introduction to Finding and Replacing Text in Aspose.Words for Java

Aspose.Words for Java is a powerful Java API that allows you to work with Word documents programmatically. One of the common tasks when dealing with Word documents is finding and replacing text. Whether you need to update placeholders in templates or perform more complex text manipulations, Aspose.Words for Java can help you achieve your goals efficiently.

## Prerequisites

Before we dive into the details of finding and replacing text, make sure you have the following prerequisites in place:

- Java Development Environment
- Aspose.Words for Java library
- A sample Word document to work with

You can download the Aspose.Words for Java library from [here](https://releases.aspose.com/words/java/).

## Finding and Replacing Simple Text

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Find and replace text
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we load a Word document, create a `DocumentBuilder`, and use the `replace` method to find and replace "old-text" with "new-text" within the document.

## Using Regular Expressions

Regular expressions provide powerful pattern matching capabilities for text search and replacement. Aspose.Words for Java supports regular expressions for more advanced find and replace operations.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Use regular expressions for finding and replacing text
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we use a regular expression pattern to find and replace text within the document.

## Ignoring Text Inside Fields

You can configure Aspose.Words to ignore text inside fields when performing find and replace operations.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance and set IgnoreFields to true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Use options when replacing text
doc.getRange().replace("text-to-replace", "new-text", options);

// Save the modified document
doc.save("modified-document.docx");
```

This is useful when you want to exclude text inside fields, such as merge fields, from being replaced.

## Ignoring Text Inside Delete Revisions

You can configure Aspose.Words to ignore text inside delete revisions during find and replace operations.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance and set IgnoreDeleted to true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Use options when replacing text
doc.getRange().replace("text-to-replace", "new-text", options);

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to exclude text that has been marked for deletion in tracked changes from being replaced.

## Ignoring Text Inside Insert Revisions

You can configure Aspose.Words to ignore text inside insert revisions during find and replace operations.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance and set IgnoreInserted to true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Use options when replacing text
doc.getRange().replace("text-to-replace", "new-text", options);

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to exclude text that has been marked as inserted in tracked changes from being replaced.

## Replacing Text with HTML

You can use Aspose.Words for Java to replace text with HTML content.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance with a custom replacing callback
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Use options when replacing text
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we use a custom `ReplaceWithHtmlEvaluator` to replace text with HTML content.

## Replacing Text in Headers and Footers

You can find and replace text within headers and footers of your Word document.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Get the collection of headers and footers
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Choose the header or footer type you want to replace text in (e.g., HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Create a FindReplaceOptions instance and apply it to the footer's range
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to perform text replacements specifically in headers and footers.

## Showing Changes for Header and Footer Orders

You can use Aspose.Words to show changes for header and footer orders in your document.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Get the first section
Section firstPageSection = doc.getFirstSection();

// Create a FindReplaceOptions instance and apply it to the document's range
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

// Replace text that affects header and footer orders
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to visualize changes related to header and footer orders in your document.

## Replacing Text with Fields

You can replace text with fields using Aspose.Words for Java.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance and set a custom replacing callback for fields
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Use options when replacing text
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we replace text with fields and specify the field type (e.g., `FieldType.FIELD_MERGE_FIELD`).

## Replacing with an Evaluator

You can use a custom evaluator to determine the replacement text dynamically.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance and set a custom replacing callback
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Use options when replacing text
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we use a custom evaluator (`MyReplaceEvaluator`) to replace text.

## Replacing with Regex

Aspose.Words for Java allows you to replace text using regular expressions.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Use regular expressions for finding and replacing text
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we use a regular expression pattern to find and replace text within the document.

## Recognizing and Substitutions Within Replacement Patterns

You can recognize and make substitutions within replacement patterns using Aspose.Words for Java.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance with UseSubstitutions set to true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Use options when replacing text with a pattern
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to perform substitutions within the replacement patterns for more advanced replacements.

## Replacing with a String

You can replace text with a simple string using Aspose.Words for Java.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Replace text with a string
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Save the modified document
doc.save("modified-document.docx");
```

In this example, we replace "text-to-replace" with "new-string" within the document.

## Using Legacy Order

You can use legacy order when performing find and replace operations.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Create a FindReplaceOptions instance and set UseLegacyOrder to true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Use options when replacing text
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to use legacy order for find and replace operations.

## Replacing Text in a Table

You can find and replace text within tables in your Word document.

```java
// Load the document
Document doc = new Document("your-document.docx");

// Get a specific table (e.g., the first table)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Use FindReplaceOptions for replacing text in the table
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Save the modified document
doc.save("modified-document.docx");
```

This allows you to perform text replacements specifically within tables.

## Complete Source Code For Finding and Replacing Text in Aspose.Words for Java

```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello _CustomerName_,");
        System.out.println("Original document text: " + doc.getRange().getText());
        doc.getRange().replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.FORWARD));
        System.out.println("Document text after replace: " + doc.getRange().getText());
        // Save the modified document
        doc.save(getArtifactsDir() + "FindAndReplace.SimpleFindReplace.docx");
    }
    @Test
    public void findAndHighlight() throws Exception
    {
        Document doc = new Document(getMyDir() + "Find and highlight.docx");
        FindReplaceOptions options = new FindReplaceOptions();
        {
            options.setReplacingCallback(new ReplaceEvaluatorFindAndHighlight()); options.setDirection(FindReplaceDirection.BACKWARD);
        }
        Pattern regex = Pattern.compile("your document");
        doc.getRange().replace(regex, "", options);
        doc.save(getArtifactsDir() + "FindAndReplace.FindAndHighlight.docx");
    }
    private static class ReplaceEvaluatorFindAndHighlight implements IReplacingCallback
    {
        /// <summary>
        /// This method is called by the Aspose.Words find and replace engine for each match.
        /// This method highlights the match string, even if it spans multiple runs.
        /// </summary>
        public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs e)
        {
            // This is a Run node that contains either the beginning or the complete match.
            Node currentNode = e.getMatchNode();
            // The first (and may be the only) run can contain text before the match, 
            // in this case it is necessary to split the run.
            if (e.getMatchOffset() > 0)
                currentNode = splitRun((Run) currentNode, e.getMatchOffset());
            // This array is used to store all nodes of the match for further highlighting.
            ArrayList<Run> runs = new ArrayList<Run>();
            // Find all runs that contain parts of the match string.
            int remainingLength = e.getMatch().group().length();
            while (
                remainingLength > 0 &&
                currentNode != null &&
                currentNode.getText().length() <= remainingLength)
            {
                runs.add((Run) currentNode);
                remainingLength -= currentNode.getText().length();
                // Select the next Run node.
                // Have to loop because there could be other nodes such as BookmarkStart etc.
                do
                {
                    currentNode = currentNode.getNextSibling();
                } while (currentNode != null && currentNode.getNodeType() != NodeType.RUN);
            }
            // Split the last run that contains the match if there is any text left.
            if (currentNode != null && remainingLength > 0)
            {
                splitRun((Run) currentNode, remainingLength);
                runs.add((Run) currentNode);
            }
            // Now highlight all runs in the sequence.
            for (Run run : runs)
                run.getFont().setHighlightColor(Color.YELLOW);
            // Signal to the replace engine to do nothing because we have already done all what we wanted.
            return ReplaceAction.SKIP;
        }
    }
    /// <summary>
    /// Splits text of the specified run into two runs.
    /// Inserts the new run just after the specified run.
    /// </summary>
    private static Run splitRun(Run run, int position)
    {
        Run afterRun = (Run) run.deepClone(true);
        afterRun.setText(run.getText().substring(position));
        run.setText(run.getText().substring((0), (0) + (position)));
        run.getParentNode().insertAfter(afterRun, run);
        return afterRun;
    }
    @Test
    public void metaCharactersInSearchPattern() throws Exception
    {
        /* meta-characters
            &p - paragraph break
            &b - section break
            &m - page break
            &l - manual line break
            */
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("This is Line 1");
        builder.writeln("This is Line 2");
        doc.getRange().replace("This is Line 1&pThis is Line 2", "This is replaced line");
        builder.moveToDocumentEnd();
        builder.write("This is Line 1");
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.writeln("This is Line 2");
        doc.getRange().replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");
        doc.save(getArtifactsDir() + "FindAndReplace.MetaCharactersInSearchPattern.docx");
    }
    @Test
    public void replaceTextContainingMetaCharacters() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getFont().setName("Arial");
        builder.writeln("First section");
        builder.writeln("  1st paragraph");
        builder.writeln("  2nd paragraph");
        builder.writeln("{insert-section}");
        builder.writeln("Second section");
        builder.writeln("  1st paragraph");
        FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
        findReplaceOptions.getApplyParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        // Double each paragraph break after word "section", add kind of underline and make it centered.
        int count = doc.getRange().replace("section&p", "section&p----------------------&p", findReplaceOptions);
        // Insert section break instead of custom text tag.
        count = doc.getRange().replace("{insert-section}", "&b", findReplaceOptions);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
    }
    @Test
    public void ignoreTextInsideFields() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Insert field with text inside.
        builder.insertField("INCLUDETEXT", "Text in field");
        FindReplaceOptions options = new FindReplaceOptions(); { options.setIgnoreFields(true); }
        Pattern regex = Pattern.compile("e");
        doc.getRange().replace(regex, "*", options);
        System.out.println(doc.getText());
        options.setIgnoreFields(false);
        doc.getRange().replace(regex, "*", options);
        System.out.println(doc.getText());
    }
    @Test
    public void ignoreTextInsideDeleteRevisions() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Insert non-revised text.
        builder.writeln("Deleted");
        builder.write("Text");
        // Remove first paragraph with tracking revisions.
        doc.startTrackRevisions("author", new Date());
        doc.getFirstSection().getBody().getFirstParagraph().remove();
        doc.stopTrackRevisions();
        FindReplaceOptions options = new FindReplaceOptions(); { options.setIgnoreDeleted(true); }
        Pattern regex = Pattern.compile("e");
        doc.getRange().replace(regex, "*", options);
        System.out.println(doc.getText());
        options.setIgnoreDeleted(false);
        doc.getRange().replace(regex, "*", options);
        System.out.println(doc.getText());
    }
    @Test
    public void ignoreTextInsideInsertRevisions() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Insert text with tracking revisions.
        doc.startTrackRevisions("author", new Date());
        builder.writeln("Inserted");
        doc.stopTrackRevisions();
        // Insert non-revised text.
        builder.write("Text");
        FindReplaceOptions options = new FindReplaceOptions(); { options.setIgnoreInserted(true); }
        Pattern regex = Pattern.compile("e");
        doc.getRange().replace(regex, "*", options);
        System.out.println(doc.getText());
        options.setIgnoreInserted(false);
        doc.getRange().replace(regex, "*", options);
        System.out.println(doc.getText());
    }
    @Test
    public void replaceHtmlTextWithMetaCharacters() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("{PLACEHOLDER}");
        FindReplaceOptions findReplaceOptions = new FindReplaceOptions(); { findReplaceOptions.setReplacingCallback(new FindAndInsertHtml()); }
        doc.getRange().replace("{PLACEHOLDER}", "<p>&ldquo;Some Text&rdquo;</p>", findReplaceOptions);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceHtmlTextWithMetaCharacters.docx");
    }
    public final static class FindAndInsertHtml implements IReplacingCallback
    {
        public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs e) throws Exception
        {
            Node currentNode = e.getMatchNode();
            DocumentBuilder builder = new DocumentBuilder((Document) e.getMatchNode().getDocument());
            builder.moveTo(currentNode);
            builder.insertHtml(e.getReplacement());
            currentNode.remove();
            return ReplaceAction.SKIP;
        }
    }
    @Test
    public void replaceTextInFooter() throws Exception
    {
        Document doc = new Document(getMyDir() + "Footer.docx");
        HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();
        HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        FindReplaceOptions options = new FindReplaceOptions(); { options.setMatchCase(false); options.setFindWholeWordsOnly(false); }
        footer.getRange().replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceTextInFooter.docx");
    }
    @Test
    public void showChangesForHeaderAndFooterOrders() throws Exception
    {
        ReplaceLog logger = new ReplaceLog();
        Document doc = new Document(getMyDir() + "Footer.docx");
        Section firstPageSection = doc.getFirstSection();
        FindReplaceOptions options = new FindReplaceOptions(); { options.setReplacingCallback(logger); }
        doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);
        doc.save(getArtifactsDir() + "FindAndReplace.ShowChangesForHeaderAndFooterOrders.docx");
        logger.clearText();
        firstPageSection.getPageSetup().setDifferentFirstPageHeaderFooter(false);
        doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);
    }
    private static class ReplaceLog implements IReplacingCallback
    {
        public int replacing(ReplacingArgs args)
        {
            mTextBuilder.append(args.getMatchNode().getText());
            return ReplaceAction.SKIP;
        }
        void clearText()
        {
            mTextBuilder.setLength(0);
        }
        private StringBuilder mTextBuilder = new StringBuilder();
    }
    @Test
    public void replaceTextWithField() throws Exception
    {
        Document doc = new Document(getMyDir() + "Replace text with fields.docx");
        FindReplaceOptions options = new FindReplaceOptions();
        {
            options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));
        }
        doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceTextWithField.docx");
    }
    public static class ReplaceTextWithFieldHandler implements IReplacingCallback
    {
        public ReplaceTextWithFieldHandler(int type)
        {
            mFieldType = type;
        }
        public int replacing(ReplacingArgs args) throws Exception {
            ArrayList<Run> runs = findAndSplitMatchRuns(args);
            DocumentBuilder builder = new DocumentBuilder((Document) args.getMatchNode().getDocument());
            builder.moveTo(runs.get(runs.size() - 1));
            // Calculate the field's name from the FieldType enumeration by removing
            // the first instance of "Field" from the text. This works for almost all of the field types.
            String fieldName = FieldType.toString(mFieldType).toUpperCase().substring(5);
            // Insert the field into the document using the specified field type and the matched text as the field name.
            // If the fields you are inserting do not require this extra parameter, it can be removed from the string below.
            builder.insertField(MessageFormat.format("{0} {1}", fieldName, args.getMatch().group(0)));
            for (Run run : runs)
                run.remove();
            return ReplaceAction.SKIP;
        }
        /// <summary>
        /// Finds and splits the match runs and returns them in an List.
        /// </summary>
        public ArrayList<Run> findAndSplitMatchRuns(ReplacingArgs args)
        {
            // This is a Run node that contains either the beginning or the complete match.
            Node currentNode = args.getMatchNode();
            // The first (and may be the only) run can contain text before the match, 
            // In this case it is necessary to split the run.
            if (args.getMatchOffset() > 0)
                currentNode = splitRun((Run) currentNode, args.getMatchOffset());
            // This array is used to store all nodes of the match for further removing.
            ArrayList<Run> runs = new ArrayList<Run>();
            // Find all runs that contain parts of the match string.
            int remainingLength = args.getMatch().group().length();
            while (
                remainingLength > 0 &&
                currentNode != null &&
                currentNode.getText().length() <= remainingLength)
            {
                runs.add((Run) currentNode);
                remainingLength -= currentNode.getText().length();
                do
                {
                    currentNode = currentNode.getNextSibling();
                } while (currentNode != null && currentNode.getNodeType() != NodeType.RUN);
            }
            // Split the last run that contains the match if there is any text left.
            if (currentNode != null && remainingLength > 0)
            {
                splitRun((Run) currentNode, remainingLength);
                runs.add((Run) currentNode);
            }
            return runs;
        }
        /// <summary>
        /// Splits text of the specified run into two runs.
        /// Inserts the new run just after the specified run.
        /// </summary>
        private Run splitRun(Run run, int position)
        {
            Run afterRun = (Run) run.deepClone(true);
            afterRun.setText(run.getText().substring(position));
            run.setText(run.getText().substring((0), (0) + (position)));
            run.getParentNode().insertAfter(afterRun, run);
            return afterRun;
        }
        private /*final*/ /*FieldType*/int mFieldType;
    }
    @Test
    public void replaceWithEvaluator() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("sad mad bad");
        FindReplaceOptions options = new FindReplaceOptions(); { options.setReplacingCallback(new MyReplaceEvaluator()); }
        doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceWithEvaluator.docx");
    }
    private static class MyReplaceEvaluator implements IReplacingCallback
    {
        /// <summary>
        /// This is called during a replace operation each time a match is found.
        /// This method appends a number to the match string and returns it as a replacement string.
        /// </summary>
        public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs e)
        {
            e.setReplacement(e.getMatch() + Integer.toString(mMatchNumber));
            mMatchNumber++;
            return ReplaceAction.REPLACE;
        }
        private int mMatchNumber;
    }
    @Test
    public void replaceWithHtml() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello <CustomerName>,");
        FindReplaceOptions options = new FindReplaceOptions();
        options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));
        doc.getRange().replace(Pattern.compile(" <CustomerName>,"), "", options);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceWithHtml.docx");
    }
    private static class ReplaceWithHtmlEvaluator implements IReplacingCallback
    {
        ReplaceWithHtmlEvaluator(FindReplaceOptions options)
        {
            mOptions = options;
        }
        /// <summary>
        /// NOTE: This is a simplistic method that will only work well when the match
        /// starts at the beginning of a run.
        /// </summary>
        public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs args) throws Exception
        {
            DocumentBuilder builder = new DocumentBuilder((Document) args.getMatchNode().getDocument());
            builder.moveTo(args.getMatchNode());
            // Replace '<CustomerName>' text with a red bold name.
            builder.insertHtml("<b><font color='red'>James Bond, </font></b>");
            args.setReplacement("");
            return ReplaceAction.REPLACE;
        }
        private /*final*/ FindReplaceOptions mOptions;
    }
    @Test
    public void replaceWithRegex() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("sad mad bad");
        FindReplaceOptions options = new FindReplaceOptions();
        doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", options);
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceWithRegex.docx");
    }
    @Test
    public void recognizeAndSubstitutionsWithinReplacementPatterns() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Jason give money to Paul.");
        Pattern regex = Pattern.compile("([A-z]+) give money to ([A-z]+)");
        FindReplaceOptions options = new FindReplaceOptions(); { options.setUseSubstitutions(true); }
        doc.getRange().replace(regex, "$2 take money from $1", options);
    }
    @Test
    public void replaceWithString() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("sad mad bad");
        doc.getRange().replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.FORWARD));
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceWithString.docx");
    }
    @Test
    public void usingLegacyOrder() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("[tag 1]");
        Shape textBox = builder.insertShape(ShapeType.TEXT_BOX, 100.0, 50.0);
        builder.writeln("[tag 3]");
        builder.moveTo(textBox.getFirstParagraph());
        builder.write("[tag 2]");
        FindReplaceOptions options = new FindReplaceOptions();
        {
            options.setReplacingCallback(new ReplacingCallback()); options.setUseLegacyOrder(true);
        }
        doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);
        doc.save(getArtifactsDir() + "FindAndReplace.UsingLegacyOrder.docx");
    }
    private static class ReplacingCallback implements IReplacingCallback
    {
        public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs e)
        {
            System.out.println(e.getMatch().group());
            return ReplaceAction.REPLACE;
        }
    }
    @Test
    public void replaceTextInTable() throws Exception
    {
        Document doc = new Document(getMyDir() + "Tables.docx");
        Table table = (Table)doc.getChild(NodeType.TABLE, 0, true);
        table.getRange().replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.FORWARD));
        table.getLastRow().getLastCell().getRange().replace("50", "20", new FindReplaceOptions(FindReplaceDirection.FORWARD));
        doc.save(getArtifactsDir() + "FindAndReplace.ReplaceTextInTable.docx");
```

## Conclusion

Aspose.Words for Java provides comprehensive capabilities for finding and replacing text within Word documents. Whether you need to perform simple text replacements or more advanced operations using regular expressions, field manipulations, or custom evaluators, Aspose.Words for Java has you covered. Make sure to explore the extensive documentation and examples provided by Aspose to harness the full potential of this powerful Java library.

## FAQ's

### How do I download Aspose.Words for Java?

You can download Aspose.Words for Java from the website by visiting [this link](https://releases.aspose.com/words/java/).

### Can I use regular expressions for text replacement?

Yes, you can use regular expressions for text replacement in Aspose.Words for Java. This allows you to perform more advanced and flexible find and replace operations.

### How can I ignore text inside fields during replacement?

To ignore text inside fields during replacement, you can set the `IgnoreFields` property of the `FindReplaceOptions` to `true`. This ensures that text within fields, such as merge fields, is excluded from the replacement.

### Can I replace text inside headers and footers?

Yes, you can replace text inside headers and footers of your Word document. Simply access the appropriate header or footer and use the `replace` method with the desired `FindReplaceOptions`.

### What is the UseLegacyOrder option for?

The `UseLegacyOrder` option in `FindReplaceOptions` allows you to use legacy order when performing find and replace operations. This can be useful in certain scenarios where legacy order behavior is desired.
