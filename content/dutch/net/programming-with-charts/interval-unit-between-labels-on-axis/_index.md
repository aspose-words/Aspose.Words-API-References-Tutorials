---
title: Intervaleenheid tussen labels op de as van een diagram
linktitle: Intervaleenheid tussen labels op de as van een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de intervaleenheid tussen labels op de as van een diagram instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om de intervaleenheid tussen labels op de as van een diagram in te stellen. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en de aslabels aanpast.

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

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een kolomdiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we vijf items toe met de bijbehorende waarden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Stap 4: Pas de aslabels aan

 Om de intervaleenheid tussen labels op de X-as in te stellen, opent u de`AxisX` eigenschap van het diagram en stel de`TickLabelSpacing` vastgoed tot de gewenste waarde. In dit voorbeeld stellen we de afstand in op 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Stap 5: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Hiermee is de implementatie voltooid van het instellen van de intervaleenheid tussen labels op de as met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor intervaleenheid tussen labels op as met Aspose.Words voor .NET 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de intervaleenheid tussen labels op de as van een diagram kunt instellen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een kolomdiagram invoegen, reeksgegevens toevoegen en de aslabels aanpassen om de afstand tussen de labels te bepalen.

Aspose.Words voor .NET biedt krachtige functies voor het manipuleren van diagrammen in Word-documenten. Door de intervaleenheid tussen labels op de as in te stellen, kunt u de weergavedichtheid van de labels bepalen en de leesbaarheid van uw diagrammen verbeteren. Hiermee kunt u de presentatie van gegevens optimaliseren en de algehele gebruikerservaring verbeteren.

Met Aspose.Words voor .NET heeft u de flexibiliteit om verschillende aspecten van het diagram aan te passen, inclusief de aslabels. U kunt de gewenste intervaleenheid instellen om ervoor te zorgen dat de labels op de juiste afstand van elkaar staan en een duidelijke weergave van de gegevenspunten bieden.

### Veelgestelde vragen

#### Q1. Wat zijn aslabels in een diagram?
Aslabels in een diagram verwijzen naar de tekstuele weergave van waarden langs de horizontale (X-as) of verticale (Y-as) as van het diagram. Deze labels helpen bij het identificeren en interpreteren van de gegevenspunten die in het diagram zijn uitgezet. Aslabels bieden context en zorgen ervoor dat gebruikers de schaal en het bereik van waarden in het diagram kunnen begrijpen.

#### Vraag 2. Hoe kan ik de afstand tussen aslabels aanpassen?
 Om de afstand tussen aslabels in een diagram aan te passen met Aspose.Words voor .NET, kunt u toegang krijgen tot de`AxisX` of`AxisY` eigenschap van het diagram en wijzig de`TickLabelSpacing` eigendom. Door het instellen van de`TickLabelSpacing` tot een specifieke waarde, kunt u de intervaleenheid tussen de labels op de betreffende as regelen, waarbij u de afstand naar wens aanpast.

#### Q3. Kan ik een andere afstand instellen voor de X-as- en Y-aslabels?
Ja, u kunt verschillende afstanden instellen voor de X-as- en Y-aslabels met Aspose.Words voor .NET. Toegang tot de betreffende as (`AxisX` voor X-as of`AxisY` voor Y-as) van het diagram en wijzig de`TickLabelSpacing`eigenschap afzonderlijk voor elke as. Hierdoor kunt u verschillende intervaleenheden en afstanden instellen voor de labels op de X-as en Y-as, waardoor u een fijnmazige controle krijgt over de weergave van het diagram.

#### Q4. Wat is de betekenis van intervaleenheid tussen labels op de as?
De intervaleenheid tussen labels op de as bepaalt de afstand tussen opeenvolgende labels die op het diagram worden weergegeven. Door de intervaleenheid in te stellen, kunt u de dichtheid van de labels regelen en ervoor zorgen dat ze op de juiste afstand van elkaar staan om overbevolking en overlapping te voorkomen. Door de intervaleenheid aan te passen, kunt u de gegevens op een beter leesbare en visueel aantrekkelijke manier presenteren.

#### Vraag 5. Kan ik andere eigenschappen van de aslabels wijzigen?
Ja, Aspose.Words voor .NET biedt een breed scala aan eigenschappen om het uiterlijk en het gedrag van aslabels aan te passen. U kunt eigenschappen zoals lettertype, grootte, kleur, richting, uitlijning en meer wijzigen om de gewenste opmaak en stijl voor de aslabels te bereiken. De bibliotheek biedt uitgebreide controle over kaartelementen, zodat u professioneel ogende grafieken kunt maken die zijn afgestemd op uw specifieke vereisten.