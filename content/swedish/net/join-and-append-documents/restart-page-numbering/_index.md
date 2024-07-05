---
title: Starta om sidnumrering
linktitle: Starta om sidnumrering
second_title: Aspose.Words Document Processing API
description: Lär dig hur du startar om sidnumrering medan du ansluter och lägger till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/restart-page-numbering/
---

Denna handledning guidar dig genom processen för att använda funktionen Starta om sidnumrering i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till Word-dokument samtidigt som du startar om sidnumreringen i källdokumentet.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Words för .NET installerat. Du kan ladda ner den från Asposes webbplats eller installera den via NuGet.
2. Visual Studio eller någon annan C#-utvecklingsmiljö.

## Steg 1: Initiera dokumentkatalogerna

 Först måste du ställa in sökvägen till din dokumentkatalog. Ändra värdet på`dataDir` variabel till sökvägen där dina dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll- och måldokumenten

Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktör enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Ställ in källdokumentet på att starta om sidnumrering

 För att starta om sidnumreringen i källdokumentet måste du ställa in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.NewPage` och ställ in`RestartPageNumbering`egendom till`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Steg 4: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Spara det slutliga dokumentet

 Slutligen, spara det sammanslagna dokumentet med funktionen Starta om sidnumrering aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Exempel på källkod för Starta om sidnumrering med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen "Starta om sidnumrering" i C# med Aspose.Words för .NET:
 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Starta om sidnumrering med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med sidnumreringen omstartad i källdokumentet.