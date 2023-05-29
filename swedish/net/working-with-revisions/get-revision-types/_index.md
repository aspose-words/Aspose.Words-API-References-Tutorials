---
title: Skaffa revisionstyper
linktitle: Skaffa revisionstyper
second_title: Aspose.Words för .NET API Referens
description: Få versionstyper i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/get-revision-types/
---

I den här steg-för-steg-guiden kommer vi att berätta för dig hur du får de typer av revisioner i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Steg 2: Gå igenom styckena

Därefter går vi igenom styckena i dokumentet och kontrollerar vilka typer av revisioner som är kopplade till varje stycke.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Exempel på källkod för Get Revision Types med Aspose.Words för .NET

Här är den fullständiga källkoden för att få versionstyper i ett dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```
