---
title: Använd styckeformat
linktitle: Använd styckeformat
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder en styckestil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/apply-paragraph-style/
---

I den här handledningen kommer vi att gå igenom hur du använder en styckestil med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa styckeformatet.

## Steg 1: Skapa och konfigurera dokumentet

Börja med att skapa ett nytt dokument och ett tillhörande DocumentBuilder-objekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Konfigurera styckestilen

Vi kommer nu att konfigurera styckestilen med den inbyggda stilidentifieraren. Här är hur:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Steg 3: Lägg till innehåll

Vi kommer att lägga till innehåll i stycket. Här är hur:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Exempel på källkod för Apply Paragraph Style med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Apply Paragraph Style med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Med denna kod kommer du att kunna tillämpa en styckestil med Aspose.Words för .NET.

