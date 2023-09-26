---
title: Loading Text Files with Aspose.Words for Java
linktitle: Loading Text Files with Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 13
url: /java/document-loading-and-saving/loading-text-files/
---

## Complete Source Code
```java
        // Create a plaintext document in the form of a string with parts that may be interpreted as lists.
        // Upon loading, the first three lists will always be detected by Aspose.Words,
        // and List objects will be created for them after loading.
        final String TEXT_DOC = "Full stop delimiters:\n" +
                "1. First list item 1\n" +
                "2. First list item 2\n" +
                "3. First list item 3\n\n" +
                "Right bracket delimiters:\n" +
                "1) Second list item 1\n" +
                "2) Second list item 2\n" +
                "3) Second list item 3\n\n" +
                "Bullet delimiters:\n" +
                "• Third list item 1\n" +
                "• Third list item 2\n" +
                "• Third list item 3\n\n" +
                "Whitespace delimiters:\n" +
                "1 Fourth list item 1\n" +
                "2 Fourth list item 2\n" +
                "3 Fourth list item 3";
        // The fourth list, with whitespace inbetween the list number and list item contents,
        // will only be detected as a list if "DetectNumberingWithWhitespaces" in a LoadOptions object is set to true,
        // to avoid paragraphs that start with numbers being mistakenly detected as lists.
        TxtLoadOptions loadOptions = new TxtLoadOptions();
        {
            loadOptions.setDetectNumberingWithWhitespaces(true);
        }
        // Load the document while applying LoadOptions as a parameter and verify the result.
        Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
    }
    @Test
    public void handleSpacesOptions() throws Exception {
        final String TEXT_DOC = "      Line 1 \n" +
                "    Line 2   \n" +
                " Line 3       ";
        TxtLoadOptions loadOptions = new TxtLoadOptions();
        {
            loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
            loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
        }
        Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
    }
    @Test
    public void documentTextDirection() throws Exception {
        TxtLoadOptions loadOptions = new TxtLoadOptions();
        {
            loadOptions.setDocumentDirection(DocumentDirection.AUTO);
        }
        Document doc = new Document(getMyDir() + "Hebrew text.txt", loadOptions);
        Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
        System.out.println(paragraph.getParagraphFormat().getBidi());
        doc.save(getArtifactsDir() + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```
