---
title: Using Office Math Objects in Aspose.Words for Java
linktitle: Using Office Math Objects in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 13
url: /java/document-conversion-and-export/using-office-math-objects/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Office math.docx");
        OfficeMath officeMath = (OfficeMath) doc.getChild(NodeType.OFFICE_MATH, 0, true);
        // OfficeMath display type represents whether an equation is displayed inline with the text or displayed on its line.
        officeMath.setDisplayType(OfficeMathDisplayType.DISPLAY);
        officeMath.setJustification(OfficeMathJustification.LEFT);
        doc.save(getArtifactsDir() + "WorkingWithOfficeMath.MathEquations.docx");
```
