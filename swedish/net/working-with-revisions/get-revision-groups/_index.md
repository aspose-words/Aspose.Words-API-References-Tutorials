---
title: Skaffa revisionsgrupper
linktitle: Skaffa revisionsgrupper
second_title: Aspose.Words Document Processing API
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

## Slutsats

den här handledningen lärde vi oss hur man hämtar revisionsgrupperna i ett Word-dokument med Aspose.Words för .NET. Vi följde stegen för att ladda dokumentet och bläddra i granskningsgrupperna och visa detaljer som författare och recensionstyp. Du kan nu tillämpa denna kunskap för att analysera revisioner av ditt eget Word-dokument med Aspose.Words för .NET.

### FAQ's

#### F: Hur laddar man upp ett dokument i Aspose.Words för .NET?

 A: Använd`Document` klass av Aspose.Words för .NET för att ladda ett dokument från en fil. Du kan ange hela dokumentsökvägen.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Hur bläddrar man i revisionsgrupper i ett dokument i Aspose.Words för .NET?

 A: Använd`Groups` handlingens egendom`Revisions` objekt för att få samlingen av revisionsgrupper. Du kan sedan använda en loop för att gå igenom varje granskningsgrupp.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Behandla varje granskningsgrupp här
}
```

#### F: Hur får man fram författaren till en recensionsgrupp i Aspose.Words för .NET?

 A: Använd`Author` egendom av`RevisionGroup` objekt för att hämta författaren till revisionsgruppen.

```csharp
string author = group.Author;
```

#### F: Hur får man revisionstypen för en revisionsgrupp i Aspose.Words för .NET?

 A: Använd`RevisionType` egendom av`RevisionGroup`objekt för att få gruppens revisionstyp.

```csharp
string revisionType = group.RevisionType;
```