---
title: Infoga kolumndiagram i ett Word-dokument
linktitle: Infoga kolumndiagram i ett Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett kolumndiagram i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/insert-column-chart/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att infoga ett kolumndiagram i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och sparar dokumentet.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den genom att använda NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram

 Skapa en ny`Document` föremål och ett`DocumentBuilder` att bygga dokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett kolumndiagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till två kategorier och deras motsvarande värden.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Detta slutför implementeringen av att infoga ett kolumndiagram med Aspose.Words för .NET.

### Exempel på källkod för Infoga kolumndiagram med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Slutsats

den här handledningen har du lärt dig hur du infogar ett kolumndiagram i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett kolumndiagram, lägga till seriedata och spara dokumentet med diagrammet.

Aspose.Words för .NET tillhandahåller ett kraftfullt API för ordbehandling med diagram i Word-dokument. Kolumndiagram används ofta för att visa och jämföra data mellan olika kategorier eller grupper. Med Aspose.Words för .NET kan du enkelt skapa kolumndiagram som effektivt visualiserar dina data och ger värdefulla insikter.

Genom att använda Aspose.Words för .NET kan du automatisera processen att generera dokument med kolumndiagram, vilket sparar tid och ansträngning vid manuell dokumentskapande. Biblioteket erbjuder ett brett utbud av diagramtyper och anpassningsalternativ, så att du kan skapa visuellt tilltalande och datarika diagram i dina Word-dokument.

### Vanliga frågor

#### Q1. Vad är ett kolumndiagram?
Ett kolumndiagram är en typ av diagram som representerar data i vertikala staplar eller kolumner. Varje kolumn representerar vanligtvis en kategori eller grupp, och höjden eller längden på kolumnen anger värdet på data som är associerade med den kategorin. Kolumndiagram används vanligtvis för att jämföra data mellan olika kategorier eller för att spåra förändringar över tid.

#### Q2. Kan jag lägga till flera serier i kolumndiagrammet?
Ja, du kan lägga till flera serier till kolumndiagrammet med Aspose.Words för .NET. Varje serie representerar en uppsättning datapunkter med sina respektive kategorier och värden. Genom att lägga till flera serier kan du jämföra och analysera olika datauppsättningar inom samma diagram, vilket ger en heltäckande bild av dina data.

#### Q3. Kan jag anpassa utseendet på kolumndiagrammet?
Ja, med Aspose.Words för .NET kan du anpassa olika aspekter av kolumndiagrammets utseende. Du kan ändra egenskaper som seriefärg, axeletiketter, kolumnbredd och diagramområdesformatering. Biblioteket tillhandahåller en rik uppsättning API:er för att kontrollera de visuella elementen i diagrammet och skapa ett anpassat utseende som passar dina behov.

#### Q4. Kan jag spara dokumentet med det infogade kolumndiagrammet i olika format?
 Ja, Aspose.Words för .NET låter dig spara dokumentet med det infogade kolumndiagrammet i olika format, såsom DOCX, PDF, HTML och mer. Du kan välja önskat utdataformat baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet. Det infogade kolumndiagrammet kommer att bevaras i det sparade dokumentet.

#### F5. Kan jag ändra data och utseende på kolumndiagrammet efter att ha infogat det?
Ja, efter att ha infogat kolumndiagrammet i dokumentet kan du ändra dess data och utseende med hjälp av API:erna från Aspose.Words för .NET. Du kan uppdatera seriedata, ändra kolumnfärgerna, anpassa axelegenskaper och använda formateringsalternativ för att skapa dynamiska och interaktiva diagram i dina Word-dokument.