---
title: Anpassa enstaka diagramserier i ett diagram
linktitle: Anpassa enstaka diagramserier i ett diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du anpassar enstaka diagramserier i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/single-chart-series/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att anpassa enstaka diagramserier i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, kommer åt specifika serier och ändrar deras egenskaper.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den genom att använda NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram

 Skapa en ny`Document` föremål och ett`DocumentBuilder` att bygga dokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett linjediagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Få tillgång till och anpassa diagramserier

 För att ändra enstaka sjökortsserier måste du komma åt`ChartSeries` objekt i diagrammet.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Steg 4: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Detta slutför implementeringen av att anpassa en enda diagramserie med Aspose.Words för .NET.

### Exempel på källkod för Single Chart Series med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Du kan också ange om linjen som förbinder punkterna på diagrammet ska utjämnas med Catmull-Rom splines.
	series0.Smooth = true;
	series1.Smooth = true;
	// Anger om det överordnade elementet som standard ska invertera sina färger om värdet är negativt.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Slutsats

I den här handledningen har du lärt dig hur du anpassar en enda diagramserie i ett diagram med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett linjediagram, komma åt specifika diagramserier och ändra deras egenskaper för att uppnå önskad anpassning.

Aspose.Words för .NET tillhandahåller kraftfulla funktioner för att manipulera diagram i Word-dokument. Genom att komma åt enskilda diagramserier kan du tillämpa specifika ändringar för att anpassa deras utseende och beteende. Detta låter dig ändra serienamnet, aktivera utjämning av diagramlinjen, anpassa markörer för datapunkter, invertera färger för negativa värden och mer för att förbättra den visuella representationen av ditt diagram.

Att anpassa en enda diagramserie ger dig flexibiliteten att lyfta fram specifik data eller betona särskilda trender i ditt diagram. Med Aspose.Words för .NET kan du enkelt komma åt och ändra diagramserieegenskaper, vilket gör att du kan skapa visuellt tilltalande och informativa diagram i dina Word-dokument.

### Vanliga frågor

#### Q1. Kan jag anpassa flera diagramserier i ett diagram?
 Ja, du kan anpassa flera diagramserier i ett diagram med Aspose.Words för .NET. Genom att komma åt`ChartSeries`objekt i diagrammet kan du välja och ändra flera serier baserat på deras index eller specifika kriterier. Använd en slinga eller individuella tilldelningar för att ändra önskade egenskaper för varje diagramserie. På så sätt kan du tillämpa olika anpassningar på flera serier inom samma diagram.

#### Q2. Hur kan jag ändra namnet på en diagramserie?
 För att ändra namnet på en diagramserie i ett diagram med Aspose.Words för .NET måste du komma åt`Name` egendom av`ChartSeries` objekt och ställ in det till önskat namn. Serienamnet visas vanligtvis i diagramförklaringen eller dataetiketterna, vilket ger en beskrivande etikett för serien. Genom att ändra serienamnet kan du ge meningsfulla namn som återspeglar data som representeras av varje serie.

#### Q3. Vad är diagramserieutjämning?
Diagramserieutjämning är en visuell förbättringsteknik som låter dig skapa en jämn linje som förbinder punkterna på diagrammet. Den tillämpar en utjämningsalgoritm, såsom Catmull-Rom splines, för att interpolera mellan datapunkter och skapa en visuellt tilltalande kurva. För att möjliggöra serieutjämning i ett diagram med Aspose.Words för .NET, gå till`Smooth` egendom av`ChartSeries` objekt och ställ in det på`true`. Utjämning kan vara användbart för att visa trender eller mönster i data med oregelbundna fluktuationer.

#### Q4. Hur kan jag anpassa markörer för datapunkter i en diagramserie?
 För att anpassa markörer för datapunkter i en diagramserie med Aspose.Words för .NET måste du komma åt`Marker` egendom av`ChartSeries` objekt och ändra dess egenskaper som t.ex`Symbol` och`Size`. Markörer är visuella indikatorer placerade på diagrammet för att representera enskilda datapunkter. Du kan välja från en mängd olika inbyggda markörsymboler och justera deras storlek för att markera eller särskilja specifika datapunkter inom serien.

#### F5. Kan jag invertera färger för negativa värden i en diagramserie?
 Ja, du kan invertera färger för negativa värden i en diagramserie med Aspose.Words för .NET. Genom att ställa in`InvertIfNegative` egendom av`ChartSeries` invända mot`true`, kommer färgerna för datapunkter med negativa värden att inverteras, vilket gör dem visuellt åtskilda från positiva värden. Den här funktionen kan vara användbar när du jämför positiva och negativa värden i en diagramserie, vilket ger en tydlig skillnad mellan de två.