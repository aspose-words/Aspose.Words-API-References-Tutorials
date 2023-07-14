---
title: Lista Behåll källformatering
linktitle: Lista Behåll källformatering
second_title: Aspose.Words Document Processing API
description: Lär dig hur du bevarar listformatering när du ansluter och lägger till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/list-keep-source-formatting/
---

Denna handledning guidar dig genom processen att använda funktionen List Keep Source Formatting i Aspose.Words för .NET. Den här funktionen låter dig gå med i och lägga till Word-dokument samtidigt som källformateringen av listor bevaras.

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

## Steg 3: Ställ in källdokumentet på att flöda kontinuerligt

 För att säkerställa att innehållet från källdokumentet flödar kontinuerligt när det läggs till måldokumentet, måste du ställa in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Steg 4: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen, inklusive formateringen av listor, bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Spara det slutliga dokumentet

 Slutligen sparar du det sammanslagna dokumentet med funktionen List Keep Source Formatting aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Exempel på källkod för List Keep Source-formatering med Aspose.Words för .NET 

Här är den fullständiga källkoden för funktionen List Keep Source Formatting i C# med Aspose.Words för .NET:

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Lägg till innehållet i dokumentet så att det flödar kontinuerligt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen List Keep Source Formatting med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med källdokumentets listformatering bevarad.