---
title: Infoga tabell från HTML
linktitle: Infoga tabell från HTML
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar en tabell från HTML i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/insert-table-from-html/
---

den här handledningen kommer vi att lära oss hur man infogar en tabell i ett Word-dokument från HTML med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna infoga tabeller från HTML i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att starta ordbehandling med dokument- och dokumentgeneratorn, följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument
Document doc = new Document();

// Initiera dokumentgeneratorn
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Infoga tabellen från HTML
Därefter kommer vi att infoga tabellen i dokumentet med HTML-kod. Använd följande kod:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Här använder vi`InsertHtml` dokumentbyggarens metod för att infoga HTML-koden som innehåller tabellen. Den angivna HTML-koden skapar en tabell med två rader och två celler i varje rad. Du kan anpassa innehållet i tabellen genom att ändra HTML-koden efter dina behov.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det modifierade dokumentet med tabellen infogat från HTML. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Infoga tabell från HTML med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Observera att AutoFitSettings inte gäller för tabeller som infogas från HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man infogar en tabell i ett Word-dokument från HTML med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du infoga tabeller från HTML i dina Word-dokument programmatiskt. Den här funktionen låter dig konvertera och importera tabelldata från HTML-källor till dina Word-dokument.
