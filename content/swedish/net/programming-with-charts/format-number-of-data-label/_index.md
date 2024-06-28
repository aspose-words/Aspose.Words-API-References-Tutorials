---
title: Format Antal Data Etikett I Ett Diagram
linktitle: Format Antal Data Etikett I Ett Diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du formaterar antalet dataetiketter i ett diagram med Aspose.Words för .NET. Anpassa enkelt talformat för dataetiketter.
type: docs
weight: 10
url: /sv/net/programming-with-charts/format-number-of-data-label/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att formatera antalet dataetiketter i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och anpassar nummerformatet för dataetiketter.

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

 Infoga sedan ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder`. I det här exemplet infogar vi ett linjediagram.

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
	// det här fallet kommer NumberFormat att återställas till allmänt och ärvas från en källcell.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Slutsats

I den här handledningen har du lärt dig hur du formaterar antalet dataetiketter i ett diagram med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett diagram, lägga till seriedata och anpassa nummerformatet för dataetiketter enligt dina krav.

 Aspose.Words för .NET tillhandahåller ett omfattande API för ordbehandling med diagram i Word-dokument, så att du kan manipulera olika aspekter av diagrammet, inklusive dataetiketter. Genom att komma åt`DataLabels` samling associerad med en serie kan du anpassa nummerformatet för individuella dataetiketter.

API:et låter dig styra visningen av värden, ställa in olika talformat för varje dataetikett och länka talformatet till en källcell. Denna flexibilitet gör att du kan presentera numeriska data i diagram med önskad formatering, såsom valutasymboler, datumformat och procentvärden.

Genom att använda Aspose.Words för .NET kan du införliva kraftfulla kartfunktioner i dina .NET-applikationer och generera professionella dokument med fullt formaterade diagram och dataetiketter.

### Vanliga frågor

#### Q1. Vad är Aspose.Words för .NET?
Aspose.Words för .NET är ett funktionsrikt dokumentbehandlingsbibliotek som gör det möjligt för utvecklare att skapa, manipulera och spara Word-dokument programmatiskt i .NET-applikationer. Den tillhandahåller ett brett utbud av funktioner för ordbehandling med dokumentelement, inklusive diagram och dataetiketter.

#### Q2. Hur kan jag installera Aspose.Words för .NET?
Du kan installera Aspose.Words för .NET genom att ladda ner det genom att använda NuGet-pakethanteraren i Visual Studio. Sök helt enkelt efter "Apose.Words" i NuGet-pakethanteraren och installera det i ditt projekt.

#### Q3. Kan jag formatera andra aspekter av diagrammet med Aspose.Words för .NET?
Ja, Aspose.Words för .NET tillhandahåller omfattande möjligheter för att formatera olika aspekter av ett diagram. Förutom dataetiketter kan du anpassa diagramtyp, seriedata, axelegenskaper, förklaring, titel, plotområde och många andra element i diagrammet. API:et erbjuder finkornig kontroll över diagrammets utseende och formatering.

#### Q4. Kan jag använda olika nummerformat på olika dataetiketter i samma serie?
Ja, Aspose.Words för .NET låter dig tillämpa olika nummerformat på enskilda dataetiketter inom samma serie. Genom att komma åt`DataLabels` samling associerad med en serie kan du ställa in`FormatCode` egenskapen för varje dataetikett för att ange önskat nummerformat. Detta låter dig presentera numeriska värden i olika format inom samma diagram.

#### F5. Kan jag använda anpassade nummerformat för dataetiketter?
 Ja, Aspose.Words för .NET stöder anpassade nummerformat för dataetiketter. Du kan ange önskat talformat genom att ställa in`FormatCode` egenskapen för en dataetikett till en anpassad formatkod. Detta ger dig flexibiliteten att använda ett brett utbud av talformat, som valutasymboler, datumformat, procentvärden och mer.

#### F6. Kan jag spara diagrammet med formaterade dataetiketter i olika format?
Ja, Aspose.Words för .NET låter dig spara dokumentet som innehåller diagrammet med formaterade dataetiketter i olika format, såsom DOCX, PDF, HTML och mer. Du kan välja lämpligt format baserat på dina krav och använda`Save` metod för`Document` objekt för att spara dokumentet. De formaterade dataetiketterna kommer att bevaras i det sparade dokumentet.