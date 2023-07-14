---
title: Infoga enkelt kolumndiagram i ett Word-dokument
linktitle: Infoga enkelt kolumndiagram i ett Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett enkelt kolumndiagram i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/insert-simple-column-chart/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att infoga ett enkelt kolumndiagram i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och sparar dokumentet.

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

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett kolumndiagram i dokumentet. Du kan ange olika diagramtyper och storlekar enligt dina krav.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till flera serier med två kategorier vardera.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Detta slutför implementeringen av att infoga ett enkelt kolumndiagram med Aspose.Words för .NET.

### Exempel på källkod för Insert Simple Column Chart med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Du kan ange olika diagramtyper och storlekar.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Ta bort standardgenererade serier.
	seriesColl.Clear();
	// Skapa kategorinamn array, i den här handledningen har vi två kategorier.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Observera att datamatriser inte får vara tomma och matriser måste ha samma storlek.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Slutsats

den här handledningen har du lärt dig hur du infogar ett enkelt kolumndiagram i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett kolumndiagram, lägga till flera serier med kategorier och motsvarande värden och spara dokumentet med diagrammet.

Aspose.Words för .NET tillhandahåller ett kraftfullt och flexibelt API för ordbehandling med diagram i Word-dokument. Det enkla kolumndiagrammet är ett effektivt sätt att representera och jämföra data i olika kategorier. Med Aspose.Words för .NET kan du enkelt skapa kolumndiagram med anpassade data, lägga till flera serier för visuell jämförelse och anpassa diagrammets utseende enligt dina krav.

Genom att använda Aspose.Words för .NET kan du automatisera processen att generera dokument med kolumndiagram, vilket sparar tid och ansträngning vid manuell dokumentskapande. Biblioteket erbjuder ett brett utbud av diagramtyper, inklusive enkla kolumndiagram, och erbjuder olika anpassningsalternativ för att skräddarsy diagrammets utseende för att passa dina behov.

### Vanliga frågor

#### Q1. Vad är ett kolumndiagram?
Ett kolumndiagram är en typ av diagram som visar data med hjälp av vertikala staplar av varierande höjd. Varje kolumn representerar en kategori, och höjden på kolumnen motsvarar värdet för den kategorin. Kolumndiagram används vanligtvis för att jämföra data mellan olika kategorier eller för att spåra förändringar över tid.

#### Q2. Kan jag lägga till flera serier i kolumndiagrammet?
Ja, med Aspose.Words för .NET kan du lägga till flera serier i kolumndiagrammet. Varje serie representerar en uppsättning datapunkter med sina respektive kategorier och värden. Genom att lägga till flera serier kan du jämföra och analysera olika datauppsättningar inom samma kolumndiagram, vilket ger en heltäckande bild av dina data.

#### Q3. Kan jag anpassa utseendet på kolumndiagrammet?
Ja, Aspose.Words för .NET låter dig anpassa olika aspekter av kolumndiagrammets utseende. Du kan ändra egenskaper som seriefärg, axeletiketter, dataetiketter och diagramområdesformatering. Biblioteket tillhandahåller en rik uppsättning API:er för att kontrollera de visuella elementen i diagrammet och skapa ett anpassat utseende som passar dina behov.

#### Q4. Kan jag spara dokumentet med det infogade kolumndiagrammet i olika format?
 Ja, Aspose.Words för .NET låter dig spara dokumentet med det infogade kolumndiagrammet i olika format, såsom DOCX, PDF, HTML och mer. Du kan välja önskat utdataformat baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet. Det infogade kolumndiagrammet kommer att bevaras i det sparade dokumentet.

#### F5. Kan jag ändra data och utseende på kolumndiagrammet efter att ha infogat det?
Ja, efter att ha infogat kolumndiagrammet i dokumentet kan du ändra dess data och utseende med hjälp av API:erna från Aspose.Words för .NET. Du kan uppdatera seriedata med nya kategorier och värden, ändra färgerna och formateringen av kolumnerna, anpassa axelegenskaper och använda olika formateringsalternativ för att skapa dynamiska och visuellt tilltalande diagram i dina Word-dokument.