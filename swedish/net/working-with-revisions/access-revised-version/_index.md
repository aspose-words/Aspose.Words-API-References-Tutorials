---
title: Få tillgång till reviderad version
linktitle: Få tillgång till reviderad version
second_title: Aspose.Words för .NET API Referens
description: Få tillgång till en reviderad version av ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/access-revised-version/
---

den här steg-för-steg-guiden kommer vi att visa dig hur du kommer åt den reviderade versionen av ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Steg 2: Få tillgång till den reviderade versionen

Vi går nu vidare till den reviderade versionen av dokumentet.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Steg 3: Bläddra i versioner

Därefter går vi igenom de versioner som finns i dokumentet och visar specifik information för stycken som är listobjekt.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Exempel på källkod för Access Revised Version med Aspose.Words för .NET

Här är den fullständiga källkoden för att komma åt den reviderade versionen av ett dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Byt till den reviderade versionen av dokumentet.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```


