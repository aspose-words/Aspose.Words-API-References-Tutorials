---
title: Innehållskontroll för Rich Text Box
linktitle: Innehållskontroll för Rich Text Box
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en innehållskontroll för rik textruta i ett Word-dokument med Aspose.Words för .NET som möjliggör textformatering och stil.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/rich-text-box-content-control/
---

Den här handledningen visar hur man skapar en innehållskontroll för rik textruta i ett Word-dokument med Aspose.Words för .NET. Innehållskontroller för rich text box låter användare skriva in och formatera text med olika stilar och formateringsalternativ.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett dokument och StructuredDocumentTag
 Skapa en ny instans av`Document` klass och a`StructuredDocumentTag` för att representera innehållskontrollen för RTF-rutan. Specificera`SdtType.RichText` som typ och`MarkupLevel.Block` som uppmärkningsnivå för att skapa en rik textruta på blocknivå.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Steg 3: Skapa och formatera Rich Text-innehållet
Skapa ett stycke och kör för att representera innehållet med rik text. Ställ in text- och formateringsalternativ som färg, teckensnitt etc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Steg 4: Lägg till Rich Text-innehållet till innehållskontrollen
Lägg till stycket med rik textinnehåll till`ChildNodes` samling av innehållskontrollen för RTF-rutan.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Steg 5: Lägg till innehållskontrollen till dokumentet
 Lägg till innehållskontrollen för RTF-rutan till dokumentets brödtext genom att använda`AppendChild` metod för dokumentets första avsnitts kropp.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Steg 6: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Exempel på källkod för Rich Text Box Content Control med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Det är allt! Du har framgångsrikt skapat en innehållskontroll för rik textruta i ditt Word-dokument med Aspose.Words för .NET.