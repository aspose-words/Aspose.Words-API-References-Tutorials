---
title: Using HarfBuzz in Aspose.Words for Java
linktitle: Using HarfBuzz in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 15
url: /java/using-document-elements/using-harfbuzz/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "OpenType text shaping.docx");
        // When we set the text shaper factory, the layout starts to use OpenType features.
        // An Instance property returns BasicTextShaperCache object wrapping HarfBuzzTextShaperFactory.
        doc.getLayoutOptions().setTextShaperFactory(HarfBuzzTextShaperFactory.getInstance());
        doc.save(getArtifactsDir() + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```
