---
title: Skaffa revisionsgrupper
linktitle: Skaffa revisionsgrupper
second_title: Aspose.Words för .NET API Referens
description: Få versionsgrupper i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/get-revision-groups/
---

I den här steg-för-steg-guiden kommer vi att berätta hur du får versionsgrupperna i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Steg 2: Bläddra i revisionsgrupper

Därefter går vi igenom revisionsgrupperna som finns i dokumentet och visar deras detaljer, såsom författare, revisionstyp och reviderad text.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Exempel på källkod för Get Revision Groups med Aspose.Words för .NET

Här är den fullständiga källkoden för att få versionsgrupperna i ett dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```


