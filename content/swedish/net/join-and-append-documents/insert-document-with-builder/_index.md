---
title: Infoga dokument med Builder
linktitle: Infoga dokument med Builder
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett dokument i slutet av ett annat dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/insert-document-with-builder/
---

 Denna handledning förklarar hur du använder Aspose.Words för .NET för att infoga ett dokument i ett annat dokument med hjälp av`DocumentBuilder` klass. Den medföljande källkoden visar hur man infogar ett dokument i slutet av ett annat dokument samtidigt som källformateringen bevaras.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

-  Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.Releases]https://releases.aspose.com/words/net/ eller använd NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten finns.

## Steg 2: Öppna käll- och måldokumenten

 Öppna käll- och måldokumenten med hjälp av`Document` klass konstruktör. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Initiera DocumentBuilder

 Skapa en ny instans av`DocumentBuilder` klass och skicka destinationsdokumentet som en parameter.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Steg 4: Placera DocumentBuilder

Flytta`DocumentBuilder` till slutet av dokumentet med hjälp av`MoveToDocumentEnd` metod. Infoga en sidbrytning för att separera det befintliga innehållet från det infogade dokumentet.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Steg 5: Infoga källdokumentet

 Använd`InsertDocument` metod för`DocumentBuilder` klass för att infoga källdokumentet i måldokumentet. Ställ in importformatläget på`ImportFormatMode.KeepSourceFormatting` för att bevara källformateringen.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 6: Spara det ändrade dokumentet

Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Detta slutför implementeringen av att infoga ett dokument i ett annat dokument med Aspose.Words för .NET.

### Exempel på källkod för Infoga dokument med Builder med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```