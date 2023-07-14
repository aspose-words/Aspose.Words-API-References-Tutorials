---
title: Håll källan tillsammans
linktitle: Håll källan tillsammans
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder Aspose.Words för .NET för att ansluta och lägga till Word-dokument samtidigt som källinnehållet behålls tillsammans med måldokumentet.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/keep-source-together/
---

Denna handledning guidar dig genom processen att använda Keep Source Together-funktionen i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till flera Word-dokument samtidigt som källdokumentets innehåll behålls tillsammans med måldokumentets innehåll. 

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Words för .NET installerat. Du kan ladda ner den från Asposes webbplats eller installera den via NuGet.
2. Visual Studio eller någon annan C#-utvecklingsmiljö.

## Steg 1: Initiera dokumentkatalogerna

 Först måste du ställa in sökvägen till din dokumentkatalog. Ändra värdet på`dataDir`variabel till sökvägen där dina dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll- och måldokumenten

 Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktor enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Steg 3: Ställ in att källdokumentet ska visas efter destinationsdokumentets innehåll

 För att säkerställa att källdokumentet visas omedelbart efter måldokumentets innehåll, måste du ställa in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Steg 4: Ställ in "Behåll med nästa" styckeformatering för källdokument

 För att hålla ihop styckena i källdokumentet kan du iterera genom varje stycke i dokumentet och ställa in`KeepWithNext` egendom till`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Steg 5: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 6: Spara det slutliga dokumentet

Slutligen, spara det sammanslagna dokumentet med funktionen "Behåll källa tillsammans" aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Exempel på källkod för Keep Source Together med Aspose.Words för .NET 

Här är den fullständiga källkoden för funktionen "Keep Source Together" i C# med Aspose.Words för .NET:


```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ställ in att källdokumentet ska visas direkt efter måldokumentets innehåll.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Det är allt! Du har framgångsrikt implementerat Keep Source Together-funktionen med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med styckena i källdokumentet sammanhållna.