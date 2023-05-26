---
title: Format Antal dataetikett
linktitle: Format Antal dataetikett
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du formaterar antalet dataetiketter i ett diagram med Aspose.Words för .NET. Anpassa enkelt talformat för dataetiketter.
type: docs
weight: 10
url: /sv/net/programming-with-charts/format-number-of-data-label/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att formatera antalet dataetiketter i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och anpassar nummerformatet för dataetiketter.

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

 Infoga sedan ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder`I det här exemplet infogar vi ett linjediagram.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till tre kategorier och deras motsvarande värden.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Steg 4: Anpassa nummerformatet för dataetiketter

 För att formatera antalet dataetiketter, gå till`DataLabels` samling associerad med serien.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

I det här exemplet ställer vi in olika nummerformat för varje dataetikett. Den första dataetiketten är formaterad som en valuta, den andra som ett datum och den tredje som en procentsats.

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Detta slutför implementeringen av formateringen av antalet dataetiketter i ett diagram med Aspose.Words för .NET.

### Exempel på källkod för Format Number Of Data Label med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Ta bort standardgenererade serier.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Eller så kan du ställa in formatkod så att den länkas till en källcell,
	// i det här fallet kommer NumberFormat att återställas till allmänt och ärvas från en källcell.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```