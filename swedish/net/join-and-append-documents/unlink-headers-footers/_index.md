---
title: Ta bort länk sidhuvuden Sidfot
linktitle: Ta bort länk sidhuvuden Sidfot
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du går med i och lägger till Word-dokument samtidigt som du kopplar bort sidhuvuden och sidfötter med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/unlink-headers-footers/
---

Denna handledning guidar dig genom processen att använda funktionen Unlink Headers Footers i Aspose.Words för .NET. Den här funktionen låter dig gå med i och lägga till Word-dokument samtidigt som du tar bort länkarna för sidhuvuden och sidfötter från källdokumentet.

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

 Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktör enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Koppla bort sidhuvuden och sidfötter i källdokumentet

 För att koppla bort sidhuvuden och sidfötter i källdokumentet från att fortsätta måldokumentets sidhuvuden och sidfötter måste du ställa in`LinkToPrevious` egendom av`HeadersFooters` samling i det första avsnittet av källdokumentet till`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Steg 4: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Spara det slutliga dokumentet

 Slutligen sparar du det sammanslagna dokumentet med funktionen Unlink Headers Footers aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Exempel på källkod för Unlink Headers Footers med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen "Unlink Headers Footers" i C# med Aspose.Words för .NET:

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ta bort länkarna till sidhuvuden och sidfötter i källdokumentet för att stoppa detta
	// från att fortsätta destinationsdokumentets sidhuvuden och sidfötter.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Unlink Headers Footers med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med sidhuvuden och sidfötter från källdokumentet bortkopplade från måldokumentet.