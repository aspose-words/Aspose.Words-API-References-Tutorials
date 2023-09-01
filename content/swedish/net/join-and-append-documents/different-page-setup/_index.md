---
title: Olika sidinställningar
linktitle: Olika sidinställningar
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till ett dokument med olika sidinställningar med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/different-page-setup/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att lägga till ett dokument med olika sidinställningar till ett annat dokument. Den medföljande källkoden visar hur man ställer in olika sidinställningar för käll- och måldokumenten och säkerställer korrekt fortsättning och numrering.

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

## Steg 3: Ställ in sidinställningar för källdokumentet

 Justera sidinställningarna för källdokumentet för att säkerställa korrekt fortsättning och numrering. I det här exemplet ställer vi in avsnittets början till`SectionStart.Continuous` och starta om sidnumreringen. Vi ser också till att sidbredden, höjden och orienteringen matchar den sista delen av måldokumentet.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Steg 4: Ändra styckeformatering

 För att bibehålla korrekt formatering, iterera igenom alla stycken i källdokumentet och ställ in`KeepWithNext` egendom till`true`. Detta säkerställer att stycken håller ihop under bifogningsprocessen.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Steg 5: Lägg till källdokumentet till måldokumentet

 Använd`AppendDocument` metod för måldokumentet för att lägga till det modifierade källdokumentet till måldokumentet, bevara källformateringen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 6: Spara måldokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Detta slutför implementeringen av att lägga till ett dokument med olika sidinställningar med Aspose.Words för .NET.

### Exempel på källkod för Different Page Setup med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ställ in källdokumentet att fortsätta direkt efter slutet av måldokumentet.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Starta om sidnumreringen i början av källdokumentet.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// För att säkerställa att detta inte händer när källdokumentet har andra sidinställningar, se till att
	//inställningarna är identiska mellan den sista delen av måldokumentet.
	// Om det finns ytterligare fortlöpande avsnitt som följer i källdokumentet,
	// detta måste upprepas för dessa avsnitt.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Iterera igenom alla avsnitt i källdokumentet.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```