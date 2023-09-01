---
title: Enkelt Bifoga dokument
linktitle: Enkelt Bifoga dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du går med i och lägger till Word-dokument med bevarad formatering med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/simple-append-document/
---

Denna handledning guidar dig genom processen att använda funktionen Simple Append Document i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till Word-dokument utan ytterligare alternativ.

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

## Steg 3: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 4: Spara det slutliga dokumentet

 Slutligen sparar du det sammanslagna dokumentet med funktionen Simple Append Document med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Exempel på källkod för Simple Append Document med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen "Simple Append Document" i C# med Aspose.Words för .NET:

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Bifoga källdokumentet till måldokumentet utan extra alternativ.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Simple Append Document med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med bevarad källformatering.