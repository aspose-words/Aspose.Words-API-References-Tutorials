---
title: Bifoga dokument till tomt
linktitle: Bifoga dokument till tomt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till ett dokument till ett tomt måldokument i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/append-document-to-blank/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att lägga till innehållet i ett dokument till ett tomt måldokument. Den medföljande källkoden visar hur man skapar ett nytt dokument, tar bort dess innehåll och sedan lägger till källdokumentet till det.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

-  Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.Releases]https://releases.aspose.com/words/net/ eller använd NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten finns.

## Steg 2: Skapa ett nytt måldokument

 Skapa en ny`Document` objekt för måldokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Steg 3: Ta bort befintligt innehåll från måldokumentet

 För att säkerställa ett rent måldokument, ta bort allt befintligt innehåll från dokumentet med hjälp av`RemoveAllChildren` metod.

```csharp
dstDoc.RemoveAllChildren();
```

## Steg 4: Lägg till källdokumentet till måldokumentet

 Lägg till innehållet i källdokumentet till måldokumentet med hjälp av`AppendDocument` metod med`ImportFormatMode.KeepSourceFormatting` alternativ.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Spara måldokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Detta slutför implementeringen av att lägga till ett dokument till ett tomt måldokument med Aspose.Words för .NET.

### Exempel på källkod för Lägg till dokument till tomt med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Måldokumentet är inte tomt, vilket ofta gör att en tom sida visas före det bifogade dokumentet.
	// Detta beror på att basdokumentet har en tom sektion och att det nya dokumentet startas på nästa sida.
	// Ta bort allt innehåll från måldokumentet innan du lägger till.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```