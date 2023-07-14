---
title: Escape URI i PDF-dokument
linktitle: Escape URI i PDF-dokument
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide Hur man undslipper URI i PDF-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/escape-uri/
---

Den här artikeln ger en steg-för-steg-guide om hur du undkommer URI i PDF-dokument med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du infogar hyperlänkar med escaped Uri i ett dokument.

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

 Använd`InsertHyperlink` metod för`DocumentBuilder` objekt för att infoga hyperlänkar i dokumentet. Uri måste rymmas med hjälp av`Uri.EscapeUriString` funktion för att undvika formatfel.

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

## Slutsats

I den här handledningen tog vi upp hur man undkommer URI i ett PDF-dokument med Aspose.Words för .NET. Genom att undvika URI:er kan du undvika formateringsfel och säkerställa att hyperlänkar tolkas och visas korrekt i PDF-dokumentet. Följ stegen som beskrivs för att infoga hyperlänkar med escaped URI i ditt PDF-dokument. Se till att fly.

### Vanliga frågor

#### F: Vad är escape-URI i ett PDF-dokument och varför är det viktigt?
S: Escape URI i ett PDF-dokument hänvisar till metoden att konvertera specialtecken i en URL till escape-sekvenser för att undvika formatfel. Detta är viktigt eftersom specialtecken i en URL kan störa URL:ens struktur och leda till feltolkning eller felaktig rendering. Genom att undvika specialtecknen garanterar vi att URL:en tolkas korrekt och visas i PDF-dokumentet.

#### F: Hur kan jag använda Aspose.Words för .NET för att undvika URI:er i ett PDF-dokument?
S: För att undvika URI:er i ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt för att bygga dokumentet.

 Använd`InsertHyperlink` metod för`DocumentBuilder` objekt för att infoga hyperlänkar i dokumentet. Se till att fly URI:n med hjälp av`Uri.EscapeUriString` funktion för att undvika formatfel.

 Använd`Save` metod för`Document` objekt för att spara dokumentet i PDF-format genom att ange namnet på utdatafilen.

#### F: Vilka är fördelarna med att fly URI:er i ett PDF-dokument?
S: Fördelarna med URI escape i ett PDF-dokument är:

Förebyggande av formatfel: URI-escape hjälper till att förhindra formatfel som orsakas av specialtecken i en URL, vilket säkerställer att URL:en tolkas och visas korrekt i PDF-dokumentet.

Kompatibilitet med PDF-läsare: Escaped URI:er stöds i allmänhet väl av PDF-läsare, vilket säkerställer bättre kompatibilitet och en konsekvent användarupplevelse.

#### F: Vilka specialtecken ska escapes i en URI?
 S: Specialtecken som måste escapes i en URI är: blanksteg, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.