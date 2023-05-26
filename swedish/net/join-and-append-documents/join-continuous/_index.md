---
title: Gå med i Kontinuerlig
linktitle: Gå med i Kontinuerlig
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du sammanfogar två dokument kontinuerligt samtidigt som du behåller formateringen med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/join-continuous/
---

Denna handledning förklarar hur man sammanfogar två dokument kontinuerligt med Aspose.Words för .NET. Den medföljande källkoden visar hur man lägger till ett dokument i slutet av ett annat dokument med bibehållen originalformatering.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten finns.

## Steg 2: Öppna käll- och måldokumenten

 Öppna käll- och måldokumenten med hjälp av`Document` klass konstruktör. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Ställ in kontinuerlig sektionsstart

 För att få källdokumentet att visas direkt efter innehållet i måldokumentet, ställ in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Steg 4: Bifoga källdokumentet

 Bifoga källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. Ställ in importformatläget på`ImportFormatMode.KeepSourceFormatting`för att bevara originalformaten från källdokumentet.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Spara det ändrade dokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Detta slutför implementeringen av att sammanfoga två dokument kontinuerligt med Aspose.Words för .NET.

### Exempel på källkod för Join Continuous med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Få dokumentet att visas direkt efter måldokumentets innehåll.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Bifoga källdokumentet med de ursprungliga stilarna som finns i källdokumentet.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```