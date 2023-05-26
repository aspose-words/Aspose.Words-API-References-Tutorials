---
title: Definiera XYAxis-egenskaper
linktitle: Definiera XYAxis-egenskaper
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du definierar XY-axelegenskaper i ett diagram med Aspose.Words för .NET. Anpassningsalternativ för X- och Y-axlarna visas.
type: docs
weight: 10
url: /sv/net/programming-with-charts/define-xyaxis-properties/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att definiera egenskaper för X- och Y-axlarna i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och anpassar axelegenskaperna.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
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