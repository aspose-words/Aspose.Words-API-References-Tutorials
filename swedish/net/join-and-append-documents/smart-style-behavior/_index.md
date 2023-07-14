---
title: Smart stilbeteende
linktitle: Smart stilbeteende
second_title: Aspose.Words Document Processing API
description: Lär dig hur du upprätthåller smart stilbeteende när du ansluter och lägger till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/smart-style-behavior/
---

Denna handledning guidar dig genom processen att använda funktionen Smart Style Behavior i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till Word-dokument samtidigt som du behåller smart stilbeteende.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Infoga en sidbrytning i destinationsdokumentet

 För att säkerställa att det bifogade innehållet visas på en ny sida i måldokumentet kan du infoga en sidbrytning med en`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Steg 4: Ställ in alternativ för smart stilbeteende

 För att aktivera smart stilbeteende under tilläggsåtgärden måste du skapa en instans av`ImportFormatOptions` och ställ in`SmartStyleBehavior` egendom till`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Steg 5: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`InsertDocument` metod för`DocumentBuilder` klass. Använd`ImportFormatMode.UseDestinationStyles` parameter och skicka`ImportFormatOptions` objekt för att upprätthålla smart stilbeteende.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Steg 6: Spara det slutliga dokumentet

 Slutligen, spara det sammanslagna dokumentet med funktionen Smart Style Behavior aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Exempel på källkod för Smart Style Behavior med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen "Smart Style Behavior" i C# med Aspose.Words för .NET:
 
```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Smart Style Behavior med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med bibehållet smart stilbeteende.