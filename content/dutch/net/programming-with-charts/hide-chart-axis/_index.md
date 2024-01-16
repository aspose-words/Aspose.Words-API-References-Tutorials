---
title: Verberg de grafiekas in een Word-document
linktitle: Verberg de grafiekas in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de diagramas in een document kunt verbergen met Aspose.Words voor .NET. Verberg de as voor een schonere en meer gerichte kaartweergave.
type: docs
weight: 10
url: /nl/net/programming-with-charts/hide-chart-axis/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om de diagramas in een document te verbergen. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en de diagramas verbergt.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden door NuGet-pakketbeheer te gebruiken om het te installeren.
- Een documentmappad waar het uitvoerdocument wordt opgeslagen.

## Stap 2: Maak een nieuw document en voeg een diagram in

 Maak een nieuwe`Document` voorwerp en een`DocumentBuilder` om het document op te bouwen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Voeg vervolgens een diagram in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder`. In dit voorbeeld voegen we een kolomdiagram in.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we vijf items en de bijbehorende waarden toe.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Stap 4: Verberg de grafiekas

 Als u de diagramas wilt verbergen, gaat u naar het bestand`AxisY` eigenschap van het diagram en stel de`Hidden`eigendom aan`true`.

```csharp
chart.AxisY.Hidden = true;
```

In dit voorbeeld verbergen we de Y-as van het diagram.

## Stap 5: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Hiermee is de implementatie van het verbergen van de grafiekas met Aspose.Words voor .NET voltooid.

### Voorbeeldbroncode voor het verbergen van de grafiekas met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
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

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de grafiekas in een Word-document kunt verbergen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een diagram maken, seriegegevens toevoegen en de diagramas verbergen om het gewenste visuele effect te bereiken.

 Aspose.Words voor .NET biedt een uitgebreide API voor woordenverwerking met diagrammen in Word-documenten, waardoor u verschillende aspecten van het diagram kunt manipuleren, inclusief aseigenschappen. Door toegang te krijgen tot de`AxisY` eigenschap van het diagram, kunt u de Y-as verbergen om deze uit de diagramvisualisatie te verwijderen.

Het verbergen van de diagramas kan handig zijn als u zich wilt concentreren op de diagramgegevens zonder afgeleid te worden door de aslijnen en labels. Het geeft de kaart een schoner en minimalistischer uiterlijk.

Door Aspose.Words voor .NET te gebruiken, kunt u eenvoudig grafiekmogelijkheden in uw .NET-toepassingen integreren en professioneel ogende documenten genereren met aangepaste grafieken en verborgen grafiekassen.

### Veelgestelde vragen

#### Q1. Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en opslaan in .NET-toepassingen. Het biedt een breed scala aan functies voor tekstverwerking met documentelementen, waaronder diagrammen en diagramassen.

#### Vraag 2. Hoe kan ik Aspose.Words voor .NET installeren?
kunt Aspose.Words voor .NET installeren door het te downloaden met behulp van NuGet-pakketbeheer in Visual Studio. Zoek eenvoudigweg naar "Aspose.Words" in de NuGet-pakketbeheerder en installeer het in uw project.

#### Q3. Kan ik zowel de X-as als de Y-as van een diagram verbergen?
 Ja, u kunt zowel de X-as als de Y-as van een diagram verbergen met Aspose.Words voor .NET. Om de X-as te verbergen, kunt u toegang krijgen tot de`AxisX` eigenschap van het diagram en stel de`Hidden`eigendom aan`true` . Op dezelfde manier kunt u, om de Y-as te verbergen, toegang krijgen tot het`AxisY` eigendom en stel de`Hidden`eigendom aan`true`. Hierdoor kunt u beide assen uit de diagramvisualisatie verwijderen.

#### Q4. Kan ik de as opnieuw weergeven nadat ik deze heb verborgen?
Ja, u kunt de grafiekas opnieuw weergeven nadat u deze hebt verborgen met Aspose.Words voor .NET. Om een verborgen as weer te geven, stelt u eenvoudigweg de`Hidden` eigendom van de corresponderende`AxisX` of`AxisY` bezwaar tegen`false`. Hierdoor wordt de as weer zichtbaar in het diagram.

#### Vraag 5. Kan ik andere eigenschappen van de diagramas aanpassen?
 Ja, met Aspose.Words voor .NET kunt u verschillende eigenschappen van de grafiekas aanpassen, zoals de astitel, labels, lijnkleur en meer. Door toegang te krijgen tot de`AxisX` En`AxisY` eigenschappen van het diagram, kunt u eigenschappen wijzigen, zoals`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, en vele anderen. Dit geeft u een nauwkeurige controle over het uiterlijk en het gedrag van de diagramas.

#### Vraag 6. Kan ik het diagram met de verborgen as in verschillende bestandsformaten opslaan?
 Ja, met Aspose.Words voor .NET kunt u het document met het diagram met een verborgen as opslaan in verschillende bestandsindelingen, zoals DOCX, PDF, HTML en meer. U kunt het gewenste uitvoerformaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan. De verborgen as blijft behouden in het opgeslagen document.