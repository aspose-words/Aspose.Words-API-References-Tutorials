---
title: Saving HTML Documents with Fixed Layout in Aspose.Words for Java
linktitle: Saving HTML Documents with Fixed Layout in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 15
url: /java/document-loading-and-saving/saving-html-documents-with-fixed-layout/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Bullet points with alternative font.docx");
        HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
        {
            saveOptions.setUseTargetMachineFonts(true);
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
    }
    @Test
    public void writeAllCssRulesInSingleFile() throws Exception {
        Document doc = new Document(getMyDir() + "Document.docx");
        // Setting this property to true restores the old behavior (separate files) for compatibility with legacy code.
        // All CSS rules are written into single file "styles.css.
        HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
        {
            saveOptions.setSaveFontFaceCssSeparately(false);
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```
