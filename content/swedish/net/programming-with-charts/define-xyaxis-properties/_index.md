---
title: Definiera XY-axelegenskaper i ett diagram
linktitle: Definiera XY-axelegenskaper i ett diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du definierar XY-axelegenskaper i ett diagram med Aspose.Words för .NET. Anpassningsalternativ för X- och Y-axlarna visas.
type: docs
weight: 10
url: /sv/net/programming-with-charts/define-xyaxis-properties/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att definiera egenskaper för X- och Y-axlarna i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och anpassar axelegenskaperna.

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

 Infoga sedan ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder`. I det här exemplet kommer vi att infoga ett områdesdiagram.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till fem datapunkter med motsvarande datum och värden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Steg 4: Anpassa X- och Y-axelegenskaper

 För att anpassa egenskaperna för X- och Y-axlarna, gå till`ChartAxis` objekt som är associerade med diagrammet.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Ändra egenskaperna för`xAxis` och`yAxis`objekt för att ställa in önskade alternativ för X- och Y-axlarna. I det här exemplet kommer vi att visa några vanliga egenskaper som kan anpassas.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Detta slutför implementeringen av att definiera XY-axelegenskaper i ett diagram med Aspose.Words för .NET.

### Exempel på källkod för Define XYAxis Properties med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Infoga diagram
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Ändra X-axeln till kategori istället för datum, så att alla punkter placeras med lika intervall på X-axeln.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // Mätt i displayenheter för Y-axeln (hundratals).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Slutsats

den här handledningen har du lärt dig hur du definierar egenskaper för X- och Y-axlarna i ett diagram med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden kan du skapa ett diagram, lägga till seriedata och anpassa axelegenskaperna för att uppfylla dina specifika krav. Aspose.Words för .NET tillhandahåller ett omfattande API för ordbehandling med diagram i Word-dokument, så att du kan manipulera olika aspekter av diagrammet, inklusive axlarna.

 Genom att komma åt`ChartAxis` objekt som är associerade med diagrammet, kan du ändra egenskaper som kategorityp, axelkors, bock, etikettpositioner, skalning och mer. Denna flexibilitet gör att du kan skräddarsy utseendet och beteendet hos diagrammets axlar för att effektivt presentera dina data.

Genom att använda Aspose.Words för .NET kan du sömlöst integrera diagramskapande och anpassningsmöjligheter i dina .NET-applikationer och automatisera genereringen av professionella dokument med rika visualiseringar.

### Vanliga frågor

#### Q1. Vad är Aspose.Words för .NET?
Aspose.Words för .NET är ett kraftfullt dokumentbehandlingsbibliotek som gör det möjligt för utvecklare att skapa, manipulera och spara Word-dokument programmatiskt i .NET-applikationer. Den tillhandahåller ett brett utbud av funktioner för ordbehandling med dokumentelement, inklusive diagram.

#### Q2. Hur kan jag installera Aspose.Words för .NET?
Du kan installera Aspose.Words för .NET genom att ladda ner det genom att använda NuGet-pakethanteraren i Visual Studio. Sök helt enkelt efter "Aspose.Words" i NuGet-pakethanteraren och installera det i ditt projekt.

#### Q3. Kan jag anpassa andra aspekter av diagrammet med Aspose.Words för .NET?
Ja, Aspose.Words för .NET erbjuder omfattande möjligheter för att anpassa olika aspekter av ett diagram. Förutom att definiera axelegenskaper kan du ändra diagramtyp, dataserie, förklaring, titel, plotområde, dataetiketter och många andra element i diagrammet. API:et erbjuder finkornig kontroll över diagrammets utseende och beteende.

#### Q4. Kan jag skapa olika typer av diagram med Aspose.Words för .NET?
Ja, Aspose.Words för .NET stöder ett brett utbud av diagramtyper, inklusive område, stapel, linje, cirkel, scatter och mer. Du kan använda`ChartType` uppräkning för att ange önskad diagramtyp när du infogar en diagramform i ett Word-dokument.

#### F5. Kan jag spara diagrammet i olika format?
 Ja, Aspose.Words för .NET låter dig spara dokumentet som innehåller diagrammet i olika format, såsom DOCX, PDF, HTML och mer. Du kan välja lämpligt format baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet.

#### F6. Kan jag tillämpa dessa tekniker på flera diagram i ett dokument?
 Ja, du kan tillämpa dessa tekniker på flera diagram i ett dokument genom att upprepa de nödvändiga stegen för varje diagram. Du kan skapa separata`Chart` och`ChartAxis` objekt för varje diagram och anpassa deras egenskaper därefter. Aspose.Words för .NET ger fullt stöd för ordbehandling med flera diagram i ett enda dokument.