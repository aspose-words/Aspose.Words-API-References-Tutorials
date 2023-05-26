---
title: Kopiera bokmärkt text
linktitle: Kopiera bokmärkt text
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du kopierar bokmärkestext från ett källdokument till ett annat dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/copy-bookmarked-text/
---

den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Kopiera bokmärkt text i Aspose.Words för .NET-biblioteket. Med den här funktionen kan du kopiera innehållet i ett specifikt bokmärke från ett källdokument till ett annat dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Laddar källdokument

 Innan vi kopierar bokmärkestexten måste vi ladda källdokumentet i en`Document` objekt som använder filsökvägen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Steg 2: Hämta källbokmärke

 Vi använder`Bookmarks` egenskapen för källdokumentintervallet för att få det specifika bokmärke vi vill kopiera:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Steg 3: Skapa måldokumentet

Vi skapar ett nytt dokument som kommer att fungera som måldokument för att kopiera bokmärkesinnehållet:

```csharp
Document dstDoc = new Document();
```

## Steg 4: Ange kopieringsplatsen

Vi anger platsen där vi vill lägga till den kopierade texten. I vårt exempel lägger vi till texten i slutet av brödtexten i den sista delen av måldokumentet:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Steg 5: Importera och kopiera bokmärkestext

 Vi använder a`NodeImporter`objekt för att importera och kopiera bokmärkestext från ett källdokument till måldokumentet:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Exempel på källkod för Kopiera bokmärkt text med Aspose.Words för .NET

Här är det fullständiga exemplet på källkoden för att demonstrera kopiering av text från ett bokmärke med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Det här är bokmärket vars innehåll vi vill kopiera.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Vi kommer att lägga till detta dokument.
	Document dstDoc = new Document();

	// Låt oss säga att vi kommer att läggas till i slutet av brödtexten i det sista avsnittet.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Om du importerar flera gånger utan ett enda sammanhang kommer det att resultera i många stilar som skapas.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Kopiera bokmärkt text från Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att kopiera innehållet i ett bokmärke från ett källdokument till ett annat dokument.