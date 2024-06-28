---
title: Lägg till kommentarer
linktitle: Lägg till kommentarer
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till kommentarer till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-comments/add-comments/
---

I den här omfattande handledningen kommer du att lära dig hur du lägger till kommentarer till ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna infoga kommentarer och anpassa deras innehåll i dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Lägg till innehåll i dokumentet
Lägg sedan till önskat innehåll i dokumentet med hjälp av DocumentBuilder-objektet. I det här exemplet lägger vi till lite text:

```csharp
builder.Write("Some text is added.");
```

## Steg 3: Skapa en kommentar och lägg till innehåll
För att lägga till en kommentar, skapa en instans av klassen Comment, skicka dokumentobjektet, författarens namn, författarens initialer och det aktuella datumet:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Lägg sedan till kommentaren till det aktuella stycket:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Lägg till innehåll i kommentaren, till exempel ett stycke och text:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Steg 4: Spara dokumentet
När du har lagt till kommentaren och dess innehåll, spara dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Exempel på källkod för Lägg till kommentarer med Aspose.Words för .NET
Här är den fullständiga källkoden för att lägga till kommentarer med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till kommentarer till ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu infoga kommentarer och anpassa deras innehåll i dina dokument.

Kommentarer är användbara för samarbete, tillhandahållande av ytterligare information eller för att göra anteckningar i ett dokument. Experimentera med olika författares namn, initialer och kommentarsinnehåll för att möta dina specifika krav.

### FAQ's

#### F: Hur kan jag lägga till en kommentar i ett Aspose.Words för .NET-dokument?

S: För att lägga till en kommentar i ett Aspose.Words för .NET-dokument måste du följa stegen som nämns i handledningen.

#### F: Kan jag formatera kommentarstext i Aspose.Words för .NET?

S: Ja, du kan formatera kommentartext i Aspose.Words för .NET med hjälp av de tillgängliga formateringsegenskaperna.

#### F: Hur kan jag hämta alla kommentarer som finns i ett dokument?

 S: Du kan hämta alla kommentarer som presenteras i ett dokument med hjälp av`Document.Comments` fast egendom.

#### F: Kan jag ta bort en specifik kommentar i Aspose.Words för .NET?

 S: Ja, du kan ta bort en specifik kommentar i Aspose.Words för .NET med hjälp av`Comment.Remove` metod.

#### F: Hur kan jag ändra texten i en befintlig kommentar i Aspose.Words för .NET?

 S: För att ändra texten i en befintlig kommentar i Aspose.Words för .NET kan du komma åt`Comment.Text` motsvarande egendom`Comment` objekt och ändra texten efter behov.