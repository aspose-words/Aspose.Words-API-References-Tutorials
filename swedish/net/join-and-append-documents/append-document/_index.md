---
title: Bifoga dokument
linktitle: Bifoga dokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du lägger till innehållet i ett dokument till ett annat med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/append-document/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att lägga till innehållet i ett dokument till ett annat. Den medföljande källkoden visar hur man öppnar käll- och måldokumenten, importerar och lägger till avsnitt från källdokumentet till måldokumentet.

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

## Steg 3: Lägg till avsnitt från källdokumentet till måldokumentet

 Gå igenom alla avsnitt i källdokumentet och importera varje avsnitt till måldokumentet med hjälp av`ImportNode` metod. Lägg sedan till det importerade avsnittet till måldokumentet.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Steg 4: Spara måldokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Detta slutför implementeringen av att lägga till ett dokument med Aspose.Words för .NET.

### Exempel på källkod för Bifoga dokument med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Gå igenom alla avsnitt i källdokumentet.
	// Sektionsnoder är omedelbara underordnade av dokumentnoden så vi kan bara räkna upp dokumentet.
	foreach (Section srcSection in srcDoc)
	{
		//Eftersom vi kopierar ett avsnitt från ett dokument till ett annat,
		// det krävs för att importera sektionsnoden till måldokumentet.
		// Detta justerar eventuella dokumentspecifika referenser till stilar, listor etc.
		//
		// Genom att importera en nod skapas en kopia av den ursprungliga noden, men kopian
		// ss redo att infogas i måldokumentet.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Nu kan den nya sektionsnoden läggas till måldokumentet.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```