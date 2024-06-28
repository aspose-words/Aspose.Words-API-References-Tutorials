---
title: Kryssa för Flerradsetikettjustering i ett diagram
linktitle: Kryssa för Flerradsetikettjustering i ett diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du justerar etiketter med flera rader i en diagramaxel med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/tick-multi-line-label-alignment/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att ställa in justeringen av etiketter med flera rader i en diagramaxel. Den medföljande källkoden visar hur man skapar ett diagram, kommer åt axeln och ändrar justeringen av ticketiketten.

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

## Slutsats

I den här handledningen har du lärt dig hur du ställer in justeringen av etiketter med flera rader i en diagramaxel med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett spridningsdiagram, komma åt diagramaxeln och ändra justeringen av bocketiketten.

Aspose.Words för .NET tillhandahåller kraftfulla funktioner för att manipulera diagram i Word-dokument. Tick-etiketter med flera rader är användbara när axeletiketter innehåller lång text som kräver lindning eller uppdelning över flera rader. Genom att ställa in kryssetikettens justering kan du styra den horisontella justeringen av flerradsetiketter inom diagramaxeln, vilket säkerställer optimal presentation och läsbarhet.

Genom att anpassa etikettjusteringen för flera rader av markeringar kan du finjustera utseendet på ditt diagram, särskilt när du har att göra med långa eller komplexa etiketter. Genom att justera etiketterna till höger, vänster, centrerat eller justerat kan du uppnå ett balanserat och visuellt tilltalande arrangemang av ticketiketter längs axeln.

Med Aspose.Words för .NET kan du enkelt komma åt och ändra egenskapen för tick-etikettjustering för en diagramaxel, vilket ger dig full kontroll över utseendet och layouten av tick-etiketter i dina Word-dokumentdiagram.

### Vanliga frågor

#### Q1. Vad är etiketter med flera rader i en diagramaxel?
Markera etiketter med flera rader i en diagramaxel hänvisar till axeletiketterna som sträcker sig över flera linjer när etiketttexten är lång eller kräver omslag för att passa inom det tillgängliga utrymmet. Istället för att avkorta etiketttexten eller orsaka visuell rörlighet, delar diagramaxeln automatiskt upp etiketterna i flera rader för att säkerställa läsbarhet. Tick-etiketter med flera rader är särskilt användbara när du hanterar långa kategori- eller värdeetiketter i diagram.

#### Q2. Kan jag anpassa justeringen av kryssetiketter i en diagramaxel?
 Ja, du kan anpassa justeringen av kryssetiketter i en diagramaxel med Aspose.Words för .NET. Genom att komma åt`TickLabelAlignment` egendom av`ChartAxis` objekt kan du ställa in önskad justering för bocketiketterna. Justeringsalternativen inkluderar vänster, höger, mitten eller justerad justering. Genom att justera justeringen kan du kontrollera den horisontella placeringen av bocketiketter längs sjökortsaxeln, vilket säkerställer korrekt läsbarhet och visuell presentation.

#### Q3. När bör jag överväga att ändra markeringens justering i en diagramaxel?
Det är fördelaktigt att ändra bocketikettens inriktning i en diagramaxel när du har långa eller flerradiga etiketter som kräver optimal presentation och läsbarhet. Genom att justera justeringen kan du se till att etiketterna är korrekt justerade och åtskilda, vilket undviker överlappning eller trunkering. Överväg att ändra justeringen av ticketiketten när du arbetar med diagram som har långa kategorinamn, utförliga värdeetiketter eller andra scenarier där standardjusteringen inte ger det önskade visuella utseendet.

#### Q4. Påverkar justeringen av ticketiketten enkelradsetiketter i en diagramaxel?
Nej, egenskapen tick label alignment påverkar inte enkelradsetiketter i en diagramaxel. Den är speciellt utformad för etiketter med flera rader som kräver omslag eller delning. Etiketter med en rad justeras baserat på standardinställningarna för justering av diagramaxeln. Egenskapen tick label alignment gäller endast etiketter som sträcker sig över flera rader, vilket gör att du kan styra justeringen av varje rad inom flerradsetiketten.

#### F5. Kan jag justera bocketiketter på olika sätt för X-axeln och Y-axeln i ett diagram?
 Ja, du kan justera kryssetiketter på olika sätt för X-axeln och Y-axeln i ett diagram med Aspose.Words för .NET. Egenskapen för kryssetikettjustering är specifik för varje diagramaxel. Genom att komma åt motsvarande`ChartAxis` objekt för X-axeln eller Y-axeln, kan du oberoende ställa in markeringens etikettjustering till olika värden. Detta ger dig flexibiliteten att justera bocketiketter på olika sätt baserat på dina specifika krav för varje axel i diagrammet.