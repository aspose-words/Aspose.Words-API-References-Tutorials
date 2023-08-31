---
title: Behåll källnumrering
linktitle: Behåll källnumrering
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till ett dokument samtidigt som du behåller källnumreringsformateringen i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/keep-source-numbering/
---

Den här handledningen förklarar hur man lägger till ett källdokument till ett måldokument samtidigt som den ursprungliga numreringsformateringen av numrerade stycken bevaras med Aspose.Words för .NET.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.Releases]https://releases.aspose.com/words/net/ eller använd NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten kommer att sparas.

## Steg 2: Skapa mål- och källdokument

 Skapa instanser av`Document` för destinations- och källdokumenten.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Behåll källnumreringen vid import

 För att bevara numreringsformateringen av numrerade stycken från källdokumentet, skapa en instans av`ImportFormatOptions` och ställ in`KeepSourceNumbering` till`true` . Använda en`NodeImporter` att importera noder från källdokumentet till måldokumentet, ange`ImportFormatMode.KeepSourceFormatting` och den`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Steg 4: Importera och lägg till stycken

 Iterera genom styckena i källdokumentet och importera varje stycke till måldokumentet med hjälp av`importer`. Lägg till de importerade noderna till måldokumentets brödtext.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Steg 5: Spara det ändrade dokumentet

 Spara det ändrade dokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Detta slutför implementeringen av att lägga till ett källdokument till ett måldokument samtidigt som den ursprungliga numreringsformateringen behålls med Aspose.Words för .NET.

### Exempel på källkod för Keep Source Numbering med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Behåll formateringen av källlistan när du importerar numrerade stycken.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```