---
title: Få revisionstyper av ord
linktitle: Få revisionstyper av ord
second_title: Aspose.Words för .NET API Referens
description: Få versionstyper av ord i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/get-revision-types/
---

I den här steg-för-steg-guiden kommer vi att berätta hur du får de typer av ordrevisioner i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Steg 2: Gå igenom styckena

Därefter går vi igenom styckena i dokumentet och kontrollerar vilka typer av ordrevisioner som är kopplade till varje stycke.

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

## Slutsats

den här handledningen lärde vi oss hur man får de typer av ordrevisioner i ett Word-dokument med Aspose.Words för .NET. Vi följde stegen för att ladda dokumentet, gå igenom styckena och kontrollera vilka typer av ordrecensioner som är kopplade till varje stycke. Nu kan du tillämpa denna kunskap för att analysera ordrecensioner i dina egna Word-dokument med Aspose.Words för .NET.

### Vanliga frågor för att få versionstyper av ord

#### F: Hur laddar man upp ett dokument i Aspose.Words för .NET?

 A: Använd`Document` klass av Aspose.Words för .NET för att ladda ett dokument från en fil. Du kan ange hela dokumentsökvägen.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Hur går jag igenom stycken i ett dokument i Aspose.Words för .NET?

 A: Använd`Paragraphs` egenskapen för dokumentsektionen för att få samlingen av stycken. Du kan sedan använda en slinga för att gå igenom varje stycke.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Bearbeta varje stycke här
}
```

#### F: Hur kontrollerar jag om ett stycke har flyttats (raderats) i Aspose.Words för .NET?

 A: Använd ett stycke`IsMoveFromRevision` egendom för att kontrollera om den har flyttats (raderad).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Paragrafen har flyttats (raderad)
}
```

#### F: Hur kontrollerar man om ett stycke har flyttats (infogats) i Aspose.Words för .NET?

 A: Använd ett stycke`IsMoveToRevision`egenskap för att kontrollera om den har flyttats (infogad).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Stycket har flyttats (infogats)
}
```