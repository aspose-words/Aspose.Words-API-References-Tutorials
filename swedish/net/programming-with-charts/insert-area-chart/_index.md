---
title: Infoga områdesdiagram i ett Word-dokument
linktitle: Infoga områdesdiagram i ett Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett områdesdiagram i ett dokument med Aspose.Words för .NET. Lägg till seriedata och spara dokumentet med diagrammet.
type: docs
weight: 10
url: /sv/net/programming-with-charts/insert-area-chart/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att infoga ett områdesdiagram i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och sparar dokumentet.

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

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett områdesdiagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till fem datapunkter med motsvarande datum och värden.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Detta slutför implementeringen av att infoga ett områdesdiagram med Aspose.Words för .NET.

### Exempel på källkod för Insert Area Chart med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Slutsats

den här handledningen har du lärt dig hur du infogar ett områdesdiagram i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett områdesdiagram, lägga till seriedata och spara dokumentet med diagrammet.

Aspose.Words för .NET tillhandahåller ett kraftfullt API för ordbehandling med diagram i Word-dokument. Med bara några rader kod kan du skapa proffsiga ytdiagram och anpassa dem efter dina krav. Ytdiagram används vanligtvis för att visa storleken och trenderna för data över tid eller kategorier.

Genom att använda Aspose.Words för .NET kan du automatisera processen att generera dokument med ytdiagram, vilket sparar tid och ansträngning vid manuell dokumentskapande. Biblioteket erbjuder ett brett utbud av diagramtyper och anpassningsalternativ, så att du kan skapa visuellt tilltalande och informativa diagram i dina Word-dokument.

### Vanliga frågor

#### Q1. Vad är Aspose.Words för .NET?
Aspose.Words för .NET är ett kraftfullt dokumentbehandlingsbibliotek som gör det möjligt för utvecklare att skapa, ändra och konvertera Word-dokument programmatiskt i .NET-applikationer. Den tillhandahåller en omfattande uppsättning API:er för ordbehandling med dokumentelement, inklusive diagram, stycken, tabeller och mer.

#### Q2. Hur installerar jag Aspose.Words för .NET?
För att installera Aspose.Words för .NET kan du använda NuGet-pakethanteraren i Visual Studio för att installera biblioteket direkt i ditt projekt. Sök helt enkelt efter "Aspose.Words" i NuGet-pakethanteraren och installera paketet.

#### Q3. Kan jag anpassa utseendet på områdesdiagrammet?
Ja, med Aspose.Words för .NET kan du anpassa olika aspekter av ytdiagrammets utseende. Du kan ändra egenskaper som diagramtitel, seriefärg, axeletiketter och diagramområdesformatering. Biblioteket tillhandahåller en rik uppsättning API:er för att kontrollera de visuella elementen i diagrammet och skapa ett anpassat utseende som passar dina behov.

#### Q4. Kan jag lägga till flera serier i ytdiagrammet?
Ja, du kan lägga till flera serier till ytdiagrammet med Aspose.Words för .NET. Varje serie representerar en uppsättning datapunkter som plottas på diagrammet. Du kan lägga till serier med olika datamängder och anpassa varje serie individuellt, inklusive dess namn, datapunkter och utseende.

#### F5. Kan jag spara dokumentet med det infogade ytdiagrammet i olika format?
 Ja, Aspose.Words för .NET låter dig spara dokumentet med det infogade ytdiagrammet i olika format, såsom DOCX, PDF, HTML och mer. Du kan välja önskat utdataformat baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet. Det infogade ytdiagrammet kommer att bevaras i det sparade dokumentet.

#### F6. Kan jag ändra data och utseende på områdesdiagrammet efter att ha infogat det?
Ja, efter att ha infogat områdesdiagrammet i dokumentet kan du ändra dess data och utseende med hjälp av API:erna som tillhandahålls av Aspose.Words för .NET. Du kan uppdatera seriedata, ändra diagramtypen, anpassa axelegenskaper och använda formateringsalternativ för att skapa dynamiska och interaktiva diagram i dina Word-dokument.