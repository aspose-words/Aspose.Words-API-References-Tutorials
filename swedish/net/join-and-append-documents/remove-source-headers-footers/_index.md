---
title: Ta bort Source Headers Footers
linktitle: Ta bort Source Headers Footers
second_title: Aspose.Words Document Processing API
description: Lär dig hur du tar bort sidhuvuden och sidfötter samtidigt som du ansluter och lägger till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/remove-source-headers-footers/
---

Denna handledning guidar dig genom processen med att använda funktionen Ta bort källa sidhuvudena sidfötter i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till Word-dokument samtidigt som du tar bort sidhuvuden och sidfötter från källdokumentet.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Words för .NET installerat. Du kan ladda ner den från Asposes webbplats eller installera den via NuGet.
2. Visual Studio eller någon annan C#-utvecklingsmiljö.

## Steg 1: Initiera dokumentkatalogerna

 Först måste du ställa in sökvägen till din dokumentkatalog. Ändra värdet på`dataDir`variabel till sökvägen där dina dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll- och måldokumenten

 Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktör enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Ta bort sidhuvuden och sidfötter från källdokumentsektioner

 För att ta bort sidhuvuden och sidfötter från varje avsnitt i källdokumentet kan du iterera genom avsnitten med en`foreach` loop och ring`ClearHeadersFooters` metod.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Steg 4: Inaktivera "LinkToPrevious"-inställningen för sidhuvuden

 Även efter att du har rensat sidhuvuden och sidfötter från källdokumentet finns det en möjlighet att inställningen "LinkToPrevious" för`HeadersFooters` kan fortfarande ställas in. För att undvika detta beteende måste du uttryckligen ställa in det på`false` för det första avsnittet`HeadersFooters` fast egendom.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Steg 5: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 6: Spara det slutliga dokumentet

 Slutligen sparar du det sammanslagna dokumentet med funktionen Ta bort källa sidhuvudena sidfötter aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Exempel på källkod för Remove Source Headers Footers med Aspose.Words för .NET 

Här är den fullständiga källkoden för funktionen "Ta bort Source Headers Footers" i C# med Aspose.Words för .NET:


```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ta bort sidhuvuden och sidfötter från var och en av avsnitten i källdokumentet.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Även efter att sidhuvuden och sidfötter har raderats från källdokumentet, inställningen "LinkToPrevious".
	// for HeadersFooters kan fortfarande ställas in. Detta gör att sidhuvuden och sidfötter fortsätter från destinationen
	// dokumentera. Detta bör ställas in på falskt för att undvika detta beteende.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Det är allt! Du har framgångsrikt implementerat funktionen Remove Source Headers Footers med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med sidhuvuden och sidfötter borttagna från källdokumentet.