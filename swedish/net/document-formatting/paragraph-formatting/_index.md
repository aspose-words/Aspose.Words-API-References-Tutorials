---
title: Styckeformatering
linktitle: Styckeformatering
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder anpassad formatering på dina stycken med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/paragraph-formatting/
---

I den här handledningen kommer vi att gå igenom hur du använder styckeformateringsfunktionen med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Skapa och konfigurera dokumentet

Börja med att skapa ett nytt dokument och ett tillhörande DocumentBuilder-objekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Formatera stycket

Vi kommer nu att tillämpa formateringen på stycket med hjälp av egenskaperna som är tillgängliga i objektet ParagraphFormat i DocumentBuilder-objektet. Här är hur:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### Exempel på källkod för styckeformatering med Aspose.Words för .NET

Här är den fullständiga källkoden för styckeformateringsfunktionen med Aspose.Words för .NET:


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.Alignment = ParagraphAlignment.Center;
	paragraphFormat.LeftIndent = 50;
	paragraphFormat.RightIndent = 50;
	paragraphFormat.SpaceAfter = 25;

	builder.Writeln(
		"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
	builder.Writeln(
		"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

	doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
	
```

Med denna kod kommer du att kunna tillämpa olika formatering på dina stycken med Aspose.Words för .NET.

