---
title: Infoga innehållsförteckning
linktitle: Infoga innehållsförteckning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar en innehållsförteckning i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-table-of-contents/
---

I den här omfattande handledningen kommer du att lära dig hur du infogar en innehållsförteckning i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna skapa en innehållsförteckning med lämpliga rubriker och sidnummer.

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

## Steg 2: Infoga en innehållsförteckning
Använd sedan metoden InsertTableOfContents i klassen DocumentBuilder för att infoga en innehållsförteckning. Ange de nödvändiga formateringsalternativen inom metoden:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Steg 3: Lägg till dokumentinnehåll
När du har infogat innehållsförteckningen lägger du till det faktiska dokumentinnehållet. Ställ in lämpliga rubrikstilar med StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Steg 4: Uppdatera innehållsförteckningen
Den nyligen infogade innehållsförteckningen kommer till en början att vara tom. För att fylla i det, uppdatera fälten i dokumentet:

```csharp
doc.UpdateFields();
```

## Steg 5: Spara dokumentet
Efter att ha infogat innehållsförteckningen och uppdaterat fälten, spara dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Exempel på källkod för Infoga innehållsförteckning med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga en innehållsförteckning med Aspose.Words för .NET:

```csharp

            string dataDir = "YOUR DOCUMENT DIRECTORY";
			
            // Initiera DocumentBuilder med Document-objekt
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            // Infoga innehållsförteckninga
			builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
            
            // Starta själva dokumentinnehållet på den andra sidan.
            builder.InsertBreak(BreakType.PageBreak);

            builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

            builder.Writeln("Heading 1");

            builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

            builder.Writeln("Heading 1.1");
            builder.Writeln("Heading 1.2");

            builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

            builder.Writeln("Heading 2");
            builder.Writeln("Heading 3");

            builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

            builder.Writeln("Heading 3.1");

            builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

            builder.Writeln("Heading 3.1.1");
            builder.Writeln("Heading 3.1.2");
            builder.Writeln("Heading 3.1.3");

            builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

            builder.Writeln("Heading 3.2");
            builder.Writeln("Heading 3.3");

            
            // Den nyligen infogade innehållsförteckningen kommer till en början att vara tom.
            // Den måste fyllas i genom att uppdatera fälten i dokumentet.
            doc.UpdateFields();
            

            doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
            
        
```
