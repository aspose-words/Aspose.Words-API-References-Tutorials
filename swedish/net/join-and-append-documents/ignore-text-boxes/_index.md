---
title: Ignorera textrutor
linktitle: Ignorera textrutor
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du lägger till ett dokument samtidigt som du ignorerar textruteformatering med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/ignore-text-boxes/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att lägga till ett dokument samtidigt som formateringen av textrutor bevaras. Den medföljande källkoden visar hur du ställer in importformatalternativen för att inkludera textrutor under bifogningsprocessen.

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

## Steg 3: Ställ in alternativ för importformat

 Skapa en instans av`ImportFormatOptions` klass och ställ in`IgnoreTextBoxes` egendom till`false`. Detta säkerställer att textrutorna inkluderas under bifogningsprocessen samtidigt som deras formatering bevaras.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Steg 4: Lägg till innehåll i textrutan

 Skapa en`NodeImporter` objekt och använd det för att importera textboxnoder från källdokumentet till måldokumentet. Iterera igenom varje stycke i källdokumentet och importera det till måldokumentet.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Steg 5: Spara måldokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Detta slutför implementeringen av att lägga till ett dokument samtidigt som textruteformateringen bevaras med Aspose.Words för .NET.

### Exempel på källkod för Ignorera textrutor med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Behåll källtextrutornas formatering när du importerar.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```