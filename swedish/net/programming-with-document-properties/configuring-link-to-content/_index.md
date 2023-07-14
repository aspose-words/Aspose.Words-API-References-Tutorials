---
title: Konfigurera länk till innehåll
linktitle: Konfigurera länk till innehåll
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ställa in länkning till innehåll i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/configuring-link-to-content/
---

I den här handledningen går vi igenom C#-källkoden för att ställa in länkning till innehåll med Aspose.Words för .NET. Den här funktionen låter dig länka till specifikt innehåll i ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Skapa dokumentet och konstruktören

I det här steget kommer vi att skapa ett nytt dokument och initiera konstruktorn. Använd följande kod:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Skapa ett bokmärke

Nu ska vi skapa ett bokmärke i dokumentet. Använd följande kod för att skapa ett bokmärke med text inuti:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Denna kod skapar ett bokmärke som heter "Mitt bokmärke" och lägger till lite text inuti.

## Steg 4: Konfigurera innehållslänken

Nu kommer vi att konfigurera länken till innehållet med hjälp av dokumentegenskaperna. Använd följande kod för att lägga till och hämta länken till innehållet:

```csharp
// Hämta listan över alla anpassade egenskaper i dokumentet.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Lägg till en innehållsbunden egenskap.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Denna kod lägger till en innehållsrelaterad egenskap som kallas "Bokmärke" med bokmärket "Mitt bokmärke". Sedan hämtar den innehållsrelaterad egenskapsinformation som länkstatus, länkkälla och egenskapsvärde.

### Exempel på källkod för att konfigurera länk till innehåll med Aspose.Words för .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Hämta en lista över alla anpassade dokumentegenskaper från filen.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Lägg till länkad till innehållsegenskap.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Du har nu lärt dig hur du konfigurerar länken till innehåll i ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt skapa och konfigurera länkar till specifikt innehåll i dina egna dokument.