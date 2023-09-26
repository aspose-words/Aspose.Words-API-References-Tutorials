---
title: Loading and Saving HTML Documents with Aspose.Words for Java
linktitle: Loading and Saving HTML Documents with Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 10
url: /java/document-loading-and-saving/loading-and-saving-html-documents/
---

## Complete Source Code
```java
        final String HTML = "\r\n                <html>\r\n                    <select name='ComboBox' size='1'>\r\n                        <option value='val1'>item1</option>\r\n                        <option value='val2'></option>                        \r\n                    </select>\r\n                </html>\r\n            ";
        HtmlLoadOptions loadOptions = new HtmlLoadOptions();
        {
            loadOptions.setPreferredControlType(HtmlControlType.STRUCTURED_DOCUMENT_TAG);
        }
        Document doc = new Document(new ByteArrayInputStream(HTML.getBytes(StandardCharsets.UTF_8)), loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.DOCX);
```
