---
title: Ställ in standardalternativ för dataetiketter i ett diagram
linktitle: Ställ in standardalternativ för dataetiketter i ett diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in standardalternativ för dataetiketter i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/default-options-for-data-labels/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att ställa in standardalternativ för dataetiketter i ett diagram. Koden som tillhandahålls visar hur man skapar ett diagram, lägger till dataserier och anpassar dataetiketterna med Aspose.Words.

## Steg 1: Konfigurera projektet

Innan vi börjar, se till att du har följande krav på plats:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den med NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram.

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

 Vi kan sedan modifiera olika egenskaper hos`labels`objekt för att ställa in önskade alternativ för dataetiketter. I det här exemplet kommer vi att aktivera visning av procent och värde, inaktivera ledarlinjer och ställa in en anpassad avgränsare.

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

## Slutsats

I den här handledningen har du lärt dig hur du ställer in standardalternativ för dataetiketter i ett diagram med Aspose.Words för .NET. Genom att följa den steg-för-steg-guiden kan du skapa ett diagram, lägga till dataserier och anpassa dataetiketterna för att uppfylla dina specifika krav. Aspose.Words för .NET tillhandahåller ett kraftfullt API för ordbehandling med diagram i Word-dokument, vilket gör att du kan manipulera olika diagramelement och uppnå önskat utseende och funktionalitet.

 Genom att ställa in egenskaperna för`ChartDataLabelCollection`objekt som är kopplat till diagramserien kan du styra visningen av dataetiketter, inklusive alternativ som att visa procentsatser, värden, ledarlinjer och anpassade avgränsare. Denna flexibilitet gör att du kan presentera data effektivt och förbättra den visuella representationen av dina diagram.

### Vanliga frågor

#### Q1. Vad är Aspose.Words för .NET?
Aspose.Words för .NET är ett bibliotek som gör det möjligt för utvecklare att skapa, manipulera och spara Word-dokument programmatiskt med hjälp av .NET-applikationer. Den tillhandahåller ett brett utbud av funktioner för ordbehandling med dokumentelement, inklusive diagram.

#### Q2. Hur kan jag installera Aspose.Words för .NET?
Du kan installera Aspose.Words för .NET genom att ladda ner det genom att använda NuGet-pakethanteraren i Visual Studio. Sök helt enkelt efter "Apose.Words" i NuGet-pakethanteraren och installera det i ditt projekt.

#### Q3. Kan jag anpassa andra aspekter av diagrammet med Aspose.Words för .NET?
Ja, Aspose.Words för .NET låter dig anpassa olika aspekter av ett diagram, såsom diagramtyp, axeletiketter, förklaring, plotområde och mer. Du kan komma åt och ändra olika egenskaper för diagramobjektet för att uppnå önskat utseende och beteende.

#### Q4. Kan jag spara diagrammet i olika format?
 Ja, Aspose.Words för .NET stöder att spara dokumentet som innehåller diagrammet i olika format, inklusive DOCX, PDF, HTML och mer. Du kan välja lämpligt format baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet.

#### F5. Kan jag tillämpa dessa tekniker på andra diagramtyper?
Ja, teknikerna som beskrivs i denna handledning kan tillämpas på andra diagramtyper som stöds av Aspose.Words för .NET. Nyckeln är att komma åt relevanta objekt och egenskaper som är specifika för den diagramtyp du ordbehandlar med.