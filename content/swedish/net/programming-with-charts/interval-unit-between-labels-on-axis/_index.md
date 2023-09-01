---
title: Intervall Enhet Mellan Etiketter På Axel Av Ett Diagram
linktitle: Intervall Enhet Mellan Etiketter På Axel Av Ett Diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in intervallenheten mellan etiketter på axeln i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att ställa in intervallenheten mellan etiketterna på axeln i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och anpassar axeletiketterna.

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
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Steg 4: Anpassa axeletiketterna

 För att ställa in intervallenheten mellan etiketter på X-axeln, gå till`AxisX` egenskapen för diagrammet och ställ in`TickLabelSpacing` egendom till önskat värde. I det här exemplet ställer vi in avståndet till 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Detta slutför implementeringen av att ställa in intervallenheten mellan etiketter på axeln med Aspose.Words för .NET.

### Exempel på källkod för Interval Unit Between Labels On Axis med Aspose.Words för .NET 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Slutsats

den här handledningen har du lärt dig hur du ställer in intervallenheten mellan etiketter på axeln i ett diagram med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett kolumndiagram, lägga till seriedata och anpassa axeletiketterna för att kontrollera avståndet mellan etiketterna.

Aspose.Words för .NET tillhandahåller kraftfulla funktioner för att manipulera diagram i Word-dokument. Genom att ställa in intervallenheten mellan etiketterna på axeln kan du kontrollera etiketternas visningstäthet och förbättra läsbarheten för dina diagram. Detta gör att du kan optimera presentationen av data och förbättra den övergripande användarupplevelsen.

Med Aspose.Words för .NET har du flexibiliteten att anpassa olika aspekter av diagrammet, inklusive axeletiketterna. Du kan ställa in önskad intervallenhet för att säkerställa att etiketterna är på lämpligt avstånd och ger en tydlig representation av datapunkterna.

### Vanliga frågor

#### Q1. Vad är axeletiketter i ett diagram?
Axeletiketter i ett diagram hänvisar till den textmässiga representationen av värden längs diagrammets horisontella (X-axel) eller vertikala (Y-axel) axel. Dessa etiketter hjälper till att identifiera och tolka datapunkterna som plottas på diagrammet. Axeletiketter ger sammanhang och låter användare förstå skalan och intervallet för värden i diagrammet.

#### Q2. Hur kan jag anpassa avståndet mellan axeletiketter?
 För att anpassa avståndet mellan axeletiketter i ett diagram med Aspose.Words för .NET kan du komma åt`AxisX` eller`AxisY` egenskapen för diagrammet och ändra`TickLabelSpacing` fast egendom. Genom att ställa in`TickLabelSpacing` till ett specifikt värde kan du styra intervallenheten mellan etiketterna på respektive axel och justera avståndet efter dina krav.

#### Q3. Kan jag ställa in olika avstånd för X-axeln och Y-axeletiketterna?
Ja, du kan ställa in olika avstånd för X-axeln och Y-axeletiketterna med Aspose.Words för .NET. Åtkomst till respektive axel (`AxisX` för X-axel eller`AxisY` för Y-axeln) i diagrammet och ändra`TickLabelSpacing`egendom individuellt för varje axel. Detta gör att du kan ha olika intervallenheter och avstånd för etiketterna på X-axeln och Y-axeln, vilket ger finkornig kontroll över diagrammets utseende.

#### Q4. Vilken betydelse har intervallenheten mellan etiketter på axeln?
Intervallenheten mellan etiketterna på axeln bestämmer avståndet mellan på varandra följande etiketter som visas på diagrammet. Genom att ställa in intervallenheten kan du kontrollera etiketternas densitet och se till att de är placerade på lämpligt avstånd för att undvika överbeläggning och överlappning. Genom att justera intervallenheten kan du presentera data på ett mer läsbart och visuellt tilltalande sätt.

#### F5. Kan jag ändra andra egenskaper för axeletiketterna?
Ja, Aspose.Words för .NET tillhandahåller ett brett utbud av egenskaper för att anpassa utseendet och beteendet hos axeletiketter. Du kan ändra egenskaper som typsnitt, storlek, färg, orientering, justering och mer för att uppnå önskad formatering och stil för axeletiketterna. Biblioteket erbjuder omfattande kontroll över diagramelement, vilket gör att du kan skapa professionella diagram som är skräddarsydda för dina specifika krav.