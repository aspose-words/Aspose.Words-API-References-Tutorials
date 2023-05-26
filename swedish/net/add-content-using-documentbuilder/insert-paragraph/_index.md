---
title: Infoga stycke
linktitle: Infoga stycke
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar formaterade stycken i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-paragraph/
---

den här omfattande handledningen kommer du att lära dig hur du infogar stycken i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna lägga till formaterade stycken i dina dokument.

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

## Steg 2: Ställ in teckensnitt och formatering
Ställ sedan in teckensnittsegenskaperna och styckeformateringen med hjälp av Font- respektive ParagraphFormat-objekten:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## Steg 3: Infoga ett stycke
Efter att ha ställt in teckensnittet och formateringen, använd Writeln-metoden i klassen DocumentBuilder för att infoga ett helt stycke:

```csharp
builder.Writeln("A whole paragraph.");
```

## Steg 4: Spara dokumentet
När du har infogat stycket sparar du dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Exempel på källkod för Infoga stycke med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga ett stycke med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du infogar formaterade stycken i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu lägga till anpassade stycken med specifika teckensnitt, formatering och justering till dina dokument.