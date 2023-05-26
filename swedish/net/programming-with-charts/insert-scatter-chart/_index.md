---
title: Infoga spridningsdiagram
linktitle: Infoga spridningsdiagram
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett punktdiagram i ett dokument med Aspose.Words för .NET. Lägg till seriedata med X- och Y-koordinater.
type: docs
weight: 10
url: /sv/net/programming-with-charts/insert-scatter-chart/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att infoga ett punktdiagram i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och sparar dokumentet.

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