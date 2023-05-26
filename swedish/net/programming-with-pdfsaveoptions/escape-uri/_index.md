---
title: Fly Uri
linktitle: Fly Uri
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg guide för att fly Uri med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/escape-uri/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder Uri escape-funktionen med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du infogar hyperlänkar med escaped Uri i ett dokument.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett dokument och en DocumentBuilder

 Därefter måste vi skapa en ny`Document` föremål och ett`DocumentBuilder` objekt för att bygga dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga hyperlänkar med escaped Uri

 Använd`InsertHyperlink` metod för`DocumentBuilder`objekt för att infoga hyperlänkar i dokumentet. Uri måste rymmas med hjälp av`Uri.EscapeUriString` funktion för att undvika formatfel.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## Steg 4: Spara dokumentet som en PDF

 Slutligen kan vi spara dokumentet som en PDF med hjälp av`Save` metod för`Document` objekt. Ange utdatafilens namn.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Det är allt ! Du har framgångsrikt infogat hyperlänkar med escaped Uri i ett dokument med Aspose.Words för .NET.

### Exempel på källkod för Uri som flyr med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```
