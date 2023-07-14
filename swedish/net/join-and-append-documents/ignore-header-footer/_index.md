---
title: Ignorera sidhuvud
linktitle: Ignorera sidhuvud
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till ett dokument samtidigt som du ignorerar sidhuvud och sidfotsinnehåll med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/ignore-header-footer/
---

Den här handledningen förklarar hur du använder Aspose.Words för .NET för att lägga till ett dokument samtidigt som du ignorerar sidhuvudet och sidfotens innehåll. Den medföljande källkoden visar hur du ställer in importformatalternativen för att utesluta sidhuvudet och sidfoten under tilläggsprocessen.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten finns.

## Steg 2: Öppna käll- och måldokumenten

 Öppna käll- och måldokumenten med hjälp av`Document` klass konstruktör. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Ställ in alternativ för importformat

 Skapa en instans av`ImportFormatOptions`klass och ställ in`IgnoreHeaderFooter` egendom till`false`. Detta säkerställer att sidhuvudet och sidfotens innehåll ingår under tilläggsprocessen.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Steg 4: Lägg till källdokumentet till måldokumentet

 Använd`AppendDocument`metod för måldokumentet för att lägga till källdokumentet. Passera`ImportFormatMode.KeepSourceFormatting` som den andra parametern och importformatalternativen som den tredje parametern.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Steg 5: Spara måldokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Detta slutför implementeringen av att lägga till ett dokument samtidigt som innehållet i sidhuvudet och sidfoten ignoreras med Aspose.Words för .NET.

### Exempel på källkod för Ignorera sidfot med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```