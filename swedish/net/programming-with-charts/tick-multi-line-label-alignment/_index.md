---
title: Markera Multi Line Label Alignment
linktitle: Markera Multi Line Label Alignment
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du justerar etiketter med flera rader i en diagramaxel med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/tick-multi-line-label-alignment/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att ställa in justeringen av etiketter med flera rader i en diagramaxel. Den medföljande källkoden visar hur man skapar ett diagram, kommer åt axeln och ändrar justeringen av ticketiketten.

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
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Steg 3: Ställ in justering av kryssetiketter

 För att ställa in justeringen av etiketter med flera rader, gå till`AxisX` egenskapen för diagrammet och ställ in`TickLabelAlignment` egenskapen till önskad inriktning. I det här exemplet ställer vi in justeringen till`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Detta slutför implementeringen av att ställa in etikettjusteringen för flera rader med hjälp av Aspose.Words för .NET.

### Exempel på källkod för Tick Multi Line Label Alignment med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Den här egenskapen har endast effekt för etiketter med flera rader.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```