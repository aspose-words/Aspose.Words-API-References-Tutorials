---
title: Standardalternativ för dataetiketter
linktitle: Standardalternativ för dataetiketter
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in standardalternativ för dataetiketter i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/default-options-for-data-labels/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att ställa in standardalternativ för dataetiketter i ett diagram. Koden som tillhandahålls visar hur man skapar ett diagram, lägger till dataserier och anpassar dataetiketterna med Aspose.Words.

## Steg 1: Konfigurera projektet

Innan vi börjar, se till att du har följande krav på plats:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram

 Låt oss först skapa en ny`Document` föremål och ett`DocumentBuilder` att bygga dokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Därefter infogar vi ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder`. I det här exemplet kommer vi att infoga ett cirkeldiagram.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till dataserier i diagrammet

Låt oss nu lägga till en dataserie i diagrammet. I det här exemplet lägger vi till tre kategorier och deras motsvarande värden.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Steg 4: Anpassa dataetiketter

 För att anpassa dataetiketterna i diagrammet måste vi komma åt`ChartDataLabelCollection` objekt som är kopplat till serien.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Vi kan sedan modifiera olika egenskaper hos`labels` objekt för att ställa in önskade alternativ för dataetiketter. I det här exemplet kommer vi att aktivera visning av procent och värde, inaktivera ledarlinjer och ställa in en anpassad avgränsare.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Steg 5: Spara dokumentet

 Slutligen sparar vi dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Detta slutför implementeringen av att ställa in standardalternativ för dataetiketter i ett diagram med Aspose.Words för .NET.

### Exempel på källkod för standardalternativ för dataetiketter med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```