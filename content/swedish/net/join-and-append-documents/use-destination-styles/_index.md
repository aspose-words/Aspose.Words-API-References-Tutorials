---
title: Använd destinationsstilar
linktitle: Använd destinationsstilar
second_title: Aspose.Words Document Processing API
description: Lär dig hur du går med i och lägger till Word-dokument samtidigt som du använder måldokumentstilar med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/use-destination-styles/
---

Denna handledning guidar dig genom processen att använda funktionen Använd destinationsstilar i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till Word-dokument samtidigt som du använder måldokumentets format.

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

Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words.`Document` klass. Uppdatera filnamnen i`Document` konstruktör enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Bifoga källdokumentet med destinationsstilar

 För att lägga till källdokumentet till måldokumentet samtidigt som du tillämpar måldokumentets format, kan du använda`AppendDocument` metod för`Document` klass med`ImportFormatMode.UseDestinationStyles` parametrar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Steg 4: Spara det slutliga dokumentet

 Slutligen, spara det sammanslagna dokumentet med funktionen Använd destinationsstilar aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Exempel på källkod för Use Destination Styles med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen "Use Destination Styles" i C# med Aspose.Words för .NET:

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Bifoga källdokumentet med hjälp av formaten för måldokumentet.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Använd destinationsstilar med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med formaten för måldokumentet.