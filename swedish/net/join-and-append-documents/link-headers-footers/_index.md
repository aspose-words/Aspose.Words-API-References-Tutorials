---
title: Länk sidhuvuden Sidfot
linktitle: Länk sidhuvuden Sidfot
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du länkar sidhuvuden och sidfötter samtidigt som du går med i och lägger till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/link-headers-footers/
---

Denna handledning guidar dig genom processen för att använda funktionen Link Headers Footers i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till flera Word-dokument samtidigt som du länkar sidhuvuden och sidfötter i källdokumentet till föregående avsnitt i måldokumentet.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Words för .NET installerat. Du kan ladda ner den från Asposes webbplats eller installera den via NuGet.
2. Visual Studio eller någon annan C#-utvecklingsmiljö.

## Steg 1: Initiera dokumentkatalogerna

 Först måste du ställa in sökvägen till din dokumentkatalog. Ändra värdet på`dataDir` variabel till sökvägen där dina dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll- och måldokumenten

 Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktor enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Ställ in det bifogade dokumentet så att det visas på en ny sida

För att säkerställa att innehållet från källdokumentet visas på en ny sida i måldokumentet måste du ställa in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Steg 4: Länka sidhuvuden och sidfötter till föregående avsnitt

 För att länka sidhuvuden och sidfötter i källdokumentet till föregående avsnitt i måldokumentet kan du använda`LinkToPrevious` metod för`HeadersFooters` samling. Genom att passera`true` som parameter åsidosätter du befintliga sidhuvuden eller sidfötter i källdokumentet.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Steg 5: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 6: Spara det slutliga dokumentet

 Slutligen, spara det sammanslagna dokumentet med de länkade sidhuvuden och sidfötter med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Exempel på källkod för Link Headers Footers med Aspose.Words för .NET 

Här är den fullständiga källkoden för funktionen "Link Headers Footers" i C# med Aspose.Words för .NET:


```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ställ in att det bifogade dokumentet ska visas på en ny sida.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Länka sidhuvuden och sidfötter i källdokumentet till föregående avsnitt.
	// Detta kommer att åsidosätta alla sidhuvuden eller sidfötter som redan finns i källdokumentet.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Link Headers Footers med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med sidhuvuden och sidfötter från källdokumentet som är länkat till föregående avsnitt i måldokumentet.