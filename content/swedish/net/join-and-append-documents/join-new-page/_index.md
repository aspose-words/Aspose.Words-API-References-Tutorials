---
title: Gå med i Ny sida
linktitle: Gå med i Ny sida
second_title: Aspose.Words Document Processing API
description: Lär dig hur du sammanfogar två dokument på en ny sida samtidigt som du bevarar formateringen med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/join-new-page/
---

Denna handledning förklarar hur man sammanfogar två dokument på en ny sida med Aspose.Words för .NET. Den medföljande källkoden visar hur du lägger till ett dokument i slutet av ett annat dokument samtidigt som du startar det bifogade dokumentet på en ny sida.

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

## Steg 3: Starta ny sidavsnitt

 För att starta det bifogade dokumentet på en ny sida, ställ in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Steg 4: Bifoga källdokumentet

 Bifoga källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. Ställ in importformatläget på`ImportFormatMode.KeepSourceFormatting` för att bevara originalformaten från källdokumentet.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Spara det ändrade dokumentet

Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Detta slutför implementeringen av att sammanfoga två dokument på en ny sida med Aspose.Words för .NET.

### Exempel på källkod för Gå med i ny sida med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ställ in det bifogade dokumentet att börja på en ny sida.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Bifoga källdokumentet med de ursprungliga stilarna som finns i källdokumentet.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```