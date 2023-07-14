---
title: Fortsätt källformatering
linktitle: Fortsätt källformatering
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till ett källdokument till ett måldokument samtidigt som du bevarar den ursprungliga formateringen med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/keep-source-formatting/
---

Denna handledning visar hur man lägger till ett källdokument till ett måldokument samtidigt som den ursprungliga formateringen av källdokumentet bevaras med Aspose.Words för .NET.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten kommer att sparas.

## Steg 2: Skapa mål- och källdokument

 Skapa instanser av`Document` för destinations- och källdokumenten.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Steg 3: Lägg till källdokumentet till måldokumentet

 Använd`AppendDocument`metod för måldokumentet för att lägga till källdokumentet. Passera`ImportFormatMode.KeepSourceFormatting` som importformatläge för att behålla originalformateringen av källdokumentet.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 4: Spara det ändrade dokumentet

 Spara det ändrade dokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Detta slutför implementeringen av att lägga till ett källdokument till ett måldokument samtidigt som den ursprungliga formateringen behålls med Aspose.Words för .NET.

### Exempel på källkod för Keep Source Formatting med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Lägg till källdokumentet till måldokumentet.
	// Passera formateringsläget för att behålla originalformateringen av källdokumentet när du importerar det.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```