---
title: Jämför alternativ
linktitle: Jämför alternativ
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att förklara C#-källkoden för funktionen Jämför alternativ med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/compare-documents/compare-options/
---

I den här handledningen kommer vi att förklara hur du använder funktionen Jämför alternativ med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Jämför dokument med anpassade alternativ

 Börja med att ladda två dokument för att jämföra. I det här exemplet kommer vi att använda`Clone()` metod för att skapa en kopia av originaldokumentet. Här är hur:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Steg 2: Konfigurera jämförelsealternativ

 Vi kommer nu att konfigurera jämförelsealternativen genom att skapa en`CompareOptions` objekt och ställ in de olika egenskaperna efter behov. Här är hur:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Steg 3: Jämför dokument med anpassade alternativ

 Vi kommer nu att använda`Compare()` metod som skickar de anpassade alternativen för att jämföra de två dokumenten. Denna metod kommer att markera ändringarna i originaldokumentet. Här är hur:

```csharp
// Jämför dokument med anpassade alternativ
docA.Compare(docB, "user", DateTime.Now, options);

// Kontrollera om dokumenten är lika
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Exempel på källkod för Compare Options med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Jämför alternativ med Aspose.Words för .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Med den här koden kan du jämföra två dokument med hjälp av anpassade alternativ för att ignorera specifika element när du jämför med Aspose.Words för .NET.

