---
title: Skapa och lägg till styckenod
linktitle: Skapa och lägg till styckenod
second_title: Aspose.Words för .NET API Referens
description: Skapa och lägg till en styckenod i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-node/create-and-add-paragraph-node/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som illustrerar hur man skapar och lägger till en styckenod med Aspose.Words för .NET.

## Steg 1: Importera nödvändiga referenser
Innan du börjar, se till att du har importerat de nödvändiga referenserna för att använda Aspose.Words för .NET i ditt projekt. Detta inkluderar att importera Aspose.Words-biblioteket och lägga till de nödvändiga namnområdena till din källfil.

```csharp
using Aspose.Words;
```

## Steg 2: Skapa ett nytt dokument
 I det här steget kommer vi att skapa ett nytt dokument med hjälp av`Document` klass.

```csharp
Document doc = new Document();
```

## Steg 3: Skapa en styckenod
 Nu kommer vi att skapa en styckenod med hjälp av`Paragraph` klass och skicka dokumentet som en parameter.

```csharp
Paragraph para = new Paragraph(doc);
```

## Steg 4: Öppna dokumentsektionen
 För att lägga till stycket i dokumentet måste vi komma åt den sista delen av dokumentet med hjälp av`LastSection` fast egendom.

```csharp
Section section = doc.LastSection;
```

## Steg 5: Lägg till styckenoden i dokumentet
 Nu när vi har dokumentavsnittet kan vi lägga till styckenoden till avsnittet med hjälp av`AppendChild` metod på sektionens`Body` fast egendom.

```csharp
section.Body.AppendChild(para);
```

## Steg 6: Spara dokumentet
 Slutligen, för att spara dokumentet, kan du använda`Save` metod genom att ange önskat utdataformat, såsom DOCX-format.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### Exempel på källkod för att skapa och lägga till paragrafnod med Aspose.Words för .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

Detta är ett komplett kodexempel för att skapa och lägga till en styckenod med Aspose.Words för .NET. Var noga med att importera nödvändiga referenser och följ stegen som beskrivits tidigare för att integrera denna kod i ditt projekt.