---
title: Dölj diagramaxeln i ett Word-dokument
linktitle: Dölj diagramaxeln i ett Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du döljer diagramaxeln i ett dokument med Aspose.Words för .NET. Dölj axeln för en renare och mer fokuserad sjökortsvisning.
type: docs
weight: 10
url: /sv/net/programming-with-charts/hide-chart-axis/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att dölja diagramaxeln i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och döljer diagramaxeln.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den genom att använda NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram.

 Skapa en ny`Document` föremål och ett`DocumentBuilder` att bygga dokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Infoga sedan ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder`. I det här exemplet infogar vi ett kolumndiagram.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till fem objekt och deras motsvarande värden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Steg 4: Dölj diagramaxeln

 För att dölja sjökortsaxeln, gå till`AxisY` egenskapen för diagrammet och ställ in`Hidden`egendom till`true`.

```csharp
chart.AxisY.Hidden = true;
```

det här exemplet döljer vi diagrammets Y-axel.

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Detta slutför implementeringen av att dölja diagramaxeln med Aspose.Words för .NET.

### Exempel på källkod för Hide Chart Axis med Aspose.Words för .NET 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Slutsats

I den här handledningen har du lärt dig hur du döljer diagramaxeln i ett Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett diagram, lägga till seriedata och dölja diagramaxeln för att uppnå önskad visuell effekt.

 Aspose.Words för .NET tillhandahåller ett omfattande API för ordbehandling med diagram i Word-dokument, vilket gör att du kan manipulera olika aspekter av diagrammet, inklusive axelegenskaper. Genom att komma åt`AxisY` egenskapen för diagrammet kan du dölja Y-axeln för att ta bort den från diagramvisualiseringen.

Att dölja sjökortsaxeln kan vara användbart när du vill fokusera på diagramdata utan distraktion av axellinjerna och etiketterna. Det ger ett renare och mer minimalistiskt utseende till diagrammet.

Genom att använda Aspose.Words för .NET kan du enkelt införliva kartfunktioner i dina .NET-applikationer och generera professionella dokument med anpassade diagram och dolda diagramaxlar.

### Vanliga frågor

#### Q1. Vad är Aspose.Words för .NET?
Aspose.Words för .NET är ett kraftfullt dokumentbehandlingsbibliotek som gör det möjligt för utvecklare att skapa, manipulera och spara Word-dokument programmatiskt i .NET-applikationer. Den tillhandahåller ett brett utbud av funktioner för ordbehandling med dokumentelement, inklusive diagram och diagramaxlar.

#### Q2. Hur kan jag installera Aspose.Words för .NET?
Du kan installera Aspose.Words för .NET genom att ladda ner det genom att använda NuGet-pakethanteraren i Visual Studio. Sök helt enkelt efter "Apose.Words" i NuGet-pakethanteraren och installera det i ditt projekt.

#### Q3. Kan jag dölja både X-axeln och Y-axeln i ett diagram?
 Ja, du kan dölja både X-axeln och Y-axeln i ett diagram med Aspose.Words för .NET. För att dölja X-axeln kan du komma åt`AxisX` egenskapen för diagrammet och ställ in`Hidden`egendom till`true` . På samma sätt, för att dölja Y-axeln, kan du komma åt`AxisY` egendom och ställ in`Hidden`egendom till`true`. Detta gör att du kan ta bort båda axlarna från diagramvisualiseringen.

#### Q4. Kan jag visa axeln igen efter att ha gömt den?
Ja, du kan visa diagramaxeln igen efter att ha gömt den med Aspose.Words för .NET. För att visa en dold axel, ställ helt enkelt in`Hidden` motsvarande egendom`AxisX` eller`AxisY` invända mot`false`. Detta kommer att göra axeln synlig igen i diagrammet.

#### F5. Kan jag anpassa andra egenskaper för diagramaxeln?
 Ja, Aspose.Words för .NET låter dig anpassa olika egenskaper för diagramaxeln, såsom axeltitel, etiketter, linjefärg och mer. Genom att komma åt`AxisX` och`AxisY` egenskaper för diagrammet kan du ändra egenskaper som`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, och många andra. Detta ger dig finkornig kontroll över diagramaxelns utseende och beteende.

#### F6. Kan jag spara diagrammet med den dolda axeln i olika filformat?
 Ja, Aspose.Words för .NET låter dig spara dokumentet som innehåller diagrammet med en dold axel i olika filformat, såsom DOCX, PDF, HTML och mer. Du kan välja önskat utdataformat baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet. Den dolda axeln kommer att bevaras i det sparade dokumentet.