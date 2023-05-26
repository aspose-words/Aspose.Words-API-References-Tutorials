---
title: Nummerformat för axel
linktitle: Nummerformat för axel
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in talformatet för en axel i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/number-format-for-axis/
---

Denna handledning förklarar hur du använder Aspose.Words för .NET för att ställa in talformatet för en axel i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och formaterar axeletiketterna.

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

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett kolumndiagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till fem objekt med motsvarande värden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Steg 4: Formatera axeletiketterna

 För att ställa in talformatet för Y-axeletiketterna, gå till`AxisY` egenskapen för diagrammet och ställ in`NumberFormat.FormatCode` egenskapen till önskat format. I det här exemplet ställer vi in formatet till "#,##0" för att visa tal med tusentals avgränsare.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Detta slutför implementeringen av att ställa in talformatet för axeln med Aspose.Words för .NET.

### Exempel på källkod för Number Format For Axis med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```