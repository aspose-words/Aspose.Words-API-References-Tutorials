---
title: Nummerformat För Axel I Ett Diagram
linktitle: Nummerformat För Axel I Ett Diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in talformatet för en axel i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/number-format-for-axis/
---

Denna handledning förklarar hur du använder Aspose.Words för .NET för att ställa in talformatet för en axel i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och formaterar axeletiketterna.

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

## Slutsats

I den här handledningen har du lärt dig hur du ställer in talformatet för en axel i ett diagram med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du skapa ett nytt dokument, infoga ett kolumndiagram, lägga till seriedata och formatera axeletiketterna för att visa siffror i ett specifikt format.

Aspose.Words för .NET tillhandahåller kraftfulla funktioner för att anpassa utseendet på diagram i Word-dokument. Genom att ställa in talformatet för axeletiketterna kan du styra hur siffror visas, inklusive alternativ som decimaler, tusentalsavgränsare, valutasymboler och mer. Detta gör att du kan presentera numerisk data på ett tydligt och meningsfullt sätt.

Med Aspose.Words för .NET har du flexibiliteten att formatera olika aspekter av diagrammet, inklusive axeletiketterna. Genom att ställa in talformatet för axeln kan du säkerställa konsekvens och förbättra läsbarheten för diagrammet, vilket gör det lättare för användare att tolka de representerade värdena.

### Vanliga frågor

#### Q1. Vilket är talformatet för en axel i ett diagram?
Talformatet för en axel i ett diagram hänvisar till formateringen som tillämpas på de numeriska värdena som visas på axeln. Det låter dig styra hur siffror presenteras, inklusive alternativ som decimaler, tusentalsavgränsare, valutasymboler, procenttecken och mer. Genom att ställa in sifferformatet kan du anpassa utseendet på numeriska data i diagrammet för att passa dina specifika krav.

#### Q2. Hur kan jag ställa in nummerformatet för axeletiketterna?
 För att ställa in talformatet för axeletiketterna i ett diagram med Aspose.Words för .NET, kan du komma åt`AxisY` egenskapen för diagrammet och ställ in`NumberFormat.FormatCode`egenskapen till önskat formatkod. Formatkoden följer syntaxen för vanliga numeriska formateringsmönster och bestämmer hur talen visas. Du kan till exempel använda "#,##0.00" för att visa tal med två decimaler och tusentalsavgränsare.

#### Q3. Kan jag ställa in olika nummerformat för X-axeln och Y-axeletiketterna?
Ja, du kan ställa in olika nummerformat för X-axeln och Y-axeletiketterna med Aspose.Words för .NET. Åtkomst till respektive axel (`AxisX` för X-axel eller`AxisY` för Y-axeln) i diagrammet och ändra`NumberFormat.FormatCode` egendom individuellt för varje axel. Detta gör att du kan tillämpa olika nummerformat på etiketterna på varje axel baserat på dina specifika krav.

#### Q4. Vilka är några vanliga nummerformatkoder jag kan använda?
Aspose.Words för .NET stöder ett brett utbud av nummerformatkoder som du kan använda för att formatera axeletiketterna i ett diagram. Några vanliga formatkoder inkluderar:

- `0` eller`#` - Visar numret utan decimaler.
- `0.00` eller`#.00` - Visar talet med två decimaler.
- `#,##0` Visar numret med tusentals avgränsare.
- `"€"0.00` - Visar siffran med eurovalutasymbolen och två decimaler.
- `"%"0` - Visar siffran i procent.

 Du kan hitta mer information om nummer[formatera koder](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) i API-referens för Aspose.Words för .NET.

#### F5. Kan jag anpassa andra egenskaper för axeletiketterna?
Ja, Aspose.Words för .NET tillhandahåller ett brett utbud av egenskaper för att anpassa utseendet och beteendet hos axeletiketter. Utöver sifferformatet kan du ändra egenskaper som typsnitt, storlek, färg, orientering, justering med mera. Detta gör att du kan anpassa axeletiketterna helt för att matcha din önskade stil och presentationskrav.