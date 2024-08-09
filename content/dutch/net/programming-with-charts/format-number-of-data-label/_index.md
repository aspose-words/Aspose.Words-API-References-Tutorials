---
title: Formatteer het aantal gegevenslabels in een grafiek
linktitle: Formatteer het aantal gegevenslabels in een grafiek
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u gegevenslabels in diagrammen kunt opmaken met Aspose.Words voor .NET met deze stapsgewijze handleiding. Verbeter moeiteloos uw Word-documenten.
type: docs
weight: 10
url: /nl/net/programming-with-charts/format-number-of-data-label/
---
## Invoering

Bij het maken van boeiende en informatieve documenten gaat het vaak om het opnemen van diagrammen met goed opgemaakte gegevenslabels. Als u een .NET-ontwikkelaar bent en uw Word-documenten wilt uitbreiden met geavanceerde grafieken, is Aspose.Words voor .NET een fantastische bibliotheek om u daarbij te helpen. In deze zelfstudie wordt u stap voor stap door het proces geleid van het opmaken van nummerlabels in een diagram met Aspose.Words voor .NET.

## Vereisten

Voordat je in de code duikt, zijn er een paar vereisten die je moet hebben:

-  Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words voor .NET-bibliotheek is geïnstalleerd. Als je het nog niet hebt geïnstalleerd, dan kan dat[download het hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: U moet een .NET-ontwikkelomgeving hebben ingesteld. Visual Studio wordt sterk aanbevolen.
- Basiskennis van C#: Bekendheid met programmeren in C# is essentieel, aangezien deze tutorial het schrijven en begrijpen van C#-code omvat.
-  Tijdelijke licentie: om Aspose.Words zonder enige beperking te gebruiken, kunt u een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).

Laten we nu eens kijken naar het stapsgewijze proces van het opmaken van nummerlabels in een diagram.

## Naamruimten importeren

Allereerst moeten we de benodigde naamruimten importeren om met Aspose.Words voor .NET te kunnen werken. Voeg de volgende regels toe bovenaan uw C#-bestand:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Stap 1: Stel uw documentenmap in

Voordat u uw Word-document kunt gaan manipuleren, moet u de map opgeven waar uw document zal worden opgeslagen. Dit is essentieel voor de latere opslagbewerking.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 2: Initialiseer het document en DocumentBuilder

 De volgende stap is het initialiseren van een nieuw`Document` en een`DocumentBuilder` . De`DocumentBuilder` is een helperklasse waarmee we de documentinhoud kunnen construeren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een diagram in het document in

 Laten we nu een diagram in het document invoegen met behulp van de`DocumentBuilder`. In deze zelfstudie gebruiken we een lijndiagram als voorbeeld.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Hier voegen we een lijndiagram in met een specifieke breedte en hoogte en stellen we de diagramtitel in.

## Stap 4: Wis de standaardreeks en voeg een nieuwe reeks toe

Standaard bevat het diagram een aantal vooraf gegenereerde reeksen. We moeten deze wissen en onze eigen reeksen met specifieke gegevenspunten toevoegen.

```csharp
// Verwijder standaard gegenereerde reeksen.
chart.Series.Clear();

// Voeg nieuwe reeksen toe met aangepaste gegevenspunten.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Stap 5: Gegevenslabels inschakelen

Om de gegevenslabels in het diagram weer te geven, moeten we ze inschakelen voor onze reeksen.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Stap 6: Gegevenslabels formatteren

De kern van deze zelfstudie is het opmaken van de gegevenslabels. Op elk gegevenslabel kunnen wij verschillende getalformaten toepassen.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Valuta-indeling
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Datumformaat
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Percentage-indeling
```

 Bovendien kunt u de indeling van een gegevenslabel aan een broncel koppelen. Wanneer gekoppeld, wordt de`NumberFormat` wordt teruggezet naar algemeen en overgenomen van de broncel.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Stap 7: Bewaar het document

Sla het document ten slotte op in de opgegeven map.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Hierdoor wordt uw document opgeslagen met de opgegeven naam en wordt ervoor gezorgd dat uw diagram met opgemaakte gegevenslabels behouden blijft.

## Conclusie

Het opmaken van gegevenslabels in een diagram met Aspose.Words voor .NET kan de leesbaarheid en professionaliteit van uw Word-documenten aanzienlijk verbeteren. Door deze stapsgewijze handleiding te volgen, zou u nu een diagram moeten kunnen maken, gegevensreeksen toevoegen en de gegevenslabels opmaken om aan uw behoeften te voldoen. Aspose.Words voor .NET is een krachtig hulpmiddel dat uitgebreide aanpassing en automatisering van Word-documenten mogelijk maakt, waardoor het van onschatbare waarde is voor .NET-ontwikkelaars.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor het programmatisch maken, manipuleren en converteren van Word-documenten met behulp van C#.

### Kan ik andere typen diagrammen opmaken met Aspose.Words voor .NET?
Ja, Aspose.Words voor .NET ondersteunt verschillende diagramtypen, waaronder staaf-, kolom-, cirkel- en meer.

### Hoe krijg ik een tijdelijke licentie voor Aspose.Words voor .NET?
 U kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).

### Is het mogelijk om gegevenslabels te koppelen aan broncellen in Excel?
Ja, u kunt gegevenslabels aan broncellen koppelen, waardoor de getalnotatie van de broncel kan worden overgenomen.

### Waar kan ik meer gedetailleerde documentatie vinden voor Aspose.Words voor .NET?
 U kunt uitgebreide documentatie vinden[hier](https://reference.aspose.com/words/net/).
