---
title: Infoga punktdiagram i Word-dokument
linktitle: Infoga punktdiagram i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett punktdiagram i ett dokument med Aspose.Words för .NET. Lägg till seriedata med X- och Y-koordinater.
type: docs
weight: 10
url: /sv/net/programming-with-charts/insert-scatter-chart/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att infoga ett punktdiagram i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och sparar dokumentet.

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

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett punktdiagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till två uppsättningar av X- och Y-koordinater.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Detta slutför implementeringen av att infoga ett punktdiagram med Aspose.Words för .NET.

### Exempel på källkod för Insert Scatter Chart med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Slutsats

I den här handledningen har du lärt dig hur du infogar ett punktdiagram i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett punktdiagram, lägga till seriedata med X- och Y-koordinater och spara dokumentet med diagrammet.

Aspose.Words för .NET tillhandahåller ett omfattande API för ordbehandling med diagram i Word-dokument. Spridningsdiagram är användbara för att visualisera och analysera data med två numeriska variabler. Med Aspose.Words för .NET kan du enkelt skapa spridningsdiagram som representerar förhållandet mellan X- och Y-värden och identifierar mönster eller trender i datan.

Genom att använda Aspose.Words för .NET kan du automatisera processen att generera dokument med punktdiagram, vilket sparar tid och ansträngning vid manuell dokumentskapande. Biblioteket erbjuder ett brett utbud av diagramtyper, inklusive punktdiagram, och erbjuder olika anpassningsalternativ för att skräddarsy diagrammets utseende efter dina behov.

### Vanliga frågor

#### Q1. Vad är ett punktdiagram?
Ett punktdiagram är en typ av diagram som visar förhållandet mellan två numeriska variabler. Den består av en serie punkter plottade på ett koordinatnät, med en variabel representerad på X-axeln och den andra variabeln representerad på Y-axeln. Spridningsdiagram används för att identifiera mönster, korrelationer eller trender mellan två uppsättningar datapunkter.

#### Q2. Kan jag lägga till flera serier i punktdiagrammet?
Ja, du kan lägga till flera serier till punktdiagrammet med Aspose.Words för .NET. Varje serie representerar en uppsättning datapunkter med sina respektive X- och Y-koordinater. Genom att lägga till flera serier kan du jämföra och analysera olika datauppsättningar inom samma punktdiagram, vilket ger en heltäckande bild av dina data.

#### Q3. Kan jag anpassa utseendet på punktdiagrammet?
Ja, med Aspose.Words för .NET kan du anpassa olika aspekter av scatter-diagrammets utseende. Du kan ändra egenskaper som seriefärg, markörform, axeletiketter och diagramområdesformatering. Biblioteket tillhandahåller en rik uppsättning API:er för att kontrollera de visuella elementen i diagrammet och skapa ett anpassat utseende som passar dina behov.

#### Q4. Kan jag spara dokumentet med det infogade punktdiagrammet i olika format?
Ja, Aspose.Words för .NET låter dig spara dokumentet med det infogade punktdiagrammet i olika format, såsom DOCX, PDF, HTML och mer. Du kan välja önskat utdataformat baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet. Det infogade punktdiagrammet kommer att bevaras i det sparade dokumentet.

#### F5. Kan jag ändra data och utseende på punktdiagrammet efter att ha infogat det?
Ja, efter att ha infogat punktdiagrammet i dokumentet kan du ändra dess data och utseende med hjälp av API:erna från Aspose.Words för .NET. Du kan uppdatera seriedata med nya X- och Y-koordinater, ändra markörens former och färger, anpassa axelegenskaper och använda formateringsalternativ för att skapa dynamiska och interaktiva diagram i dina Word-dokument.