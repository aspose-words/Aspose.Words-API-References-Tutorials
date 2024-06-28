---
title: Jämför alternativ i Word-dokument
linktitle: Jämför alternativ i Word-dokument
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att förklara C#-källkoden för funktionen Jämför alternativ i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/compare-documents/compare-options/
---
den här handledningen kommer vi att förklara hur man använder funktionen Jämför alternativ i word-dokument med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

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

## Slutsats

den här handledningen lärde vi oss hur man använder jämförelsealternativ i Aspose.Words för .NET för att anpassa jämförelseprocessen när man jämför två dokument. Genom att ange olika alternativ kan du ignorera specifika element och göra jämförelseprocessen mer flexibel. Den här funktionen låter dig ha större kontroll över jämförelseprocessen och skräddarsy den efter dina specifika krav. Aspose.Words för .NET ger kraftfulla funktioner för dokumentjämförelse, vilket gör det enkelt att identifiera skillnader mellan dokument samtidigt som man ignorerar vissa element vid behov.

### FAQ's

#### F: Vad är syftet med att använda jämförelsealternativ i Aspose.Words för .NET?

S: Jämför alternativ i Aspose.Words för .NET låter dig anpassa jämförelseprocessen när du jämför två dokument. Med dessa alternativ kan du ange vilka element som ska ignoreras under jämförelsen, såsom formateringsändringar, sidhuvuden och sidfötter, tabeller, fält, kommentarer, textrutor och fotnoter.

#### F: Hur använder jag Compare Options i Aspose.Words för .NET?

S: För att använda Jämför alternativ i Aspose.Words för .NET, följ dessa steg:
1. Ladda de två dokument som du vill jämföra till separata dokumentobjekt.
2.  Använd`Clone()` metod för att skapa en kopia av originaldokumentet.
3.  Skapa en`CompareOptions` objekt och ställ in dess egenskaper för att anpassa jämförelseprocessen. Du kan ange vilka element som ska ignoreras under jämförelsen.
4.  Använd`Compare()` metod på ett av dokumenten och skicka det andra dokumentet och`CompareOptions` objekt som parametrar. Denna metod kommer att jämföra dokumenten baserat på de angivna alternativen och markera ändringarna i originaldokumentet.
5.  Kolla`Revisions` originalhandlingens egendom. Om antalet är noll betyder det att dokumenten är identiska, med tanke på de angivna alternativen.

#### F: Vilka är de vanliga alternativen i CompareOptions?

S: De vanliga alternativen i CompareOptions inkluderar:
- `IgnoreFormatting`: Ignorerar ändringar i formateringen.
- `IgnoreHeadersAndFooters`: Ignorerar ändringar i sidhuvuden och sidfötter.
- `IgnoreCaseChanges`: Ignorerar ändringar av skiftläge (versaler/gemener).
- `IgnoreTables`: Ignorerar ändringar i tabeller.
- `IgnoreFields`: Ignorerar ändringar i fält.
- `IgnoreComments`: Ignorerar ändringar i kommentarer.
- `IgnoreTextboxes`Ignorerar ändringar i textrutor.
- `IgnoreFootnotes`: Ignorerar ändringar i fotnoter.

#### F: Kan jag använda anpassade alternativ för specifika element under dokumentjämförelse?

 S: Ja, du kan använda anpassade alternativ för specifika element under dokumentjämförelse. Genom att ställa in egenskaperna för`CompareOptions` I enlighet med detta kan du välja vilka element som ska ignoreras och vilka som ska beaktas under jämförelsen.