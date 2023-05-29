---
title: Skaffa föräldernod
linktitle: Skaffa föräldernod
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du får föräldranoden för ett specifikt element med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-node/get-parent-node/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man skaffar föräldernoden med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
```

## Steg 2: Skapa ett nytt dokument
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass.

```csharp
Document doc = new Document();
```

## Steg 3: Gå till föräldranoden
För att få föräldernoden för en specifik nod måste vi först komma åt den noden. I det här exemplet kommer vi åt dokumentets första underordnade nod, som vanligtvis är ett avsnitt.

```csharp
Node section = doc.FirstChild;
```

## Steg 4: Kontrollera föräldranoden
Nu när vi har den specifika noden kan vi kontrollera om dess överordnade nod matchar själva dokumentet. I det här exemplet jämför vi den överordnade noden med dokumentet med hjälp av likhetsoperatorn (`==`) och visa resultatet.

```csharp
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

### Exempel på källkod för att få överordnad nod med Aspose.Words för .NET


```csharp
Document doc = new Document();

// Sektionen är den första underordnade noden i dokumentet.
Node section = doc.FirstChild;

// Sektionens överordnade nod är dokumentet.
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

Detta är ett komplett kodexempel för att få föräldernoden för en specifik nod med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.
