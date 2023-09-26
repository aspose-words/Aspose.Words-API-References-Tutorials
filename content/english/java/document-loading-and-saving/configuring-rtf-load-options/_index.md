---
title: Configuring RTF Load Options in Aspose.Words for Java
linktitle: Configuring RTF Load Options in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 12
url: /java/document-loading-and-saving/configuring-rtf-load-options/
---

## Complete Source Code
```java
        RtfLoadOptions loadOptions = new RtfLoadOptions();
        {
            loadOptions.setRecognizeUtf8Text(true);
        }
        Document doc = new Document(getMyDir() + "UTF-8 characters.rtf", loadOptions);
        doc.save(getArtifactsDir() + "WorkingWithRtfLoadOptions.RecognizeUtf8Text.rtf");
```
