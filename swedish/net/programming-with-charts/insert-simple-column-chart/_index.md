---
title: Infoga enkelt kolumndiagram
linktitle: Infoga enkelt kolumndiagram
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett enkelt kolumndiagram i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/insert-simple-column-chart/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att infoga ett enkelt kolumndiagram i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och sparar dokumentet.

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
	// Sökväg till din dokumentkatalog
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