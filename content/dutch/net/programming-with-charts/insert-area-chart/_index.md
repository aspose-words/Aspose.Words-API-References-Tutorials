---
title: Vlakdiagram invoegen in een Word-document
linktitle: Vlakdiagram invoegen in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een vlakdiagram in een document invoegt met Aspose.Words voor .NET. Voeg seriegegevens toe en sla het document op met het diagram.
type: docs
weight: 10
url: /nl/net/programming-with-charts/insert-area-chart/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om een vlakdiagram in een document in te voegen. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en het document opslaat.

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

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een vlakdiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we vijf gegevenspunten toe met bijbehorende datums en waarden.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Hiermee is de implementatie van het invoegen van een vlakdiagram met Aspose.Words voor .NET voltooid.

### Voorbeeldbroncode voor vlakdiagram invoegen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Conclusie

In deze zelfstudie hebt u geleerd hoe u een vlakdiagram in een Word-document kunt invoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een vlakdiagram invoegen, seriegegevens toevoegen en het document met het diagram opslaan.

Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met grafieken in Word-documenten. Met slechts een paar regels code kunt u professioneel ogende vlakdiagrammen maken en deze aanpassen aan uw vereisten. Vlakdiagrammen worden vaak gebruikt om de omvang en trends van gegevens in de loop van de tijd of categorieën weer te geven.

Door Aspose.Words voor .NET te gebruiken, kunt u het proces van het genereren van documenten met vlakdiagrammen automatiseren, waardoor u tijd en moeite bespaart bij het handmatig maken van documenten. De bibliotheek biedt een breed scala aan diagramtypen en aanpassingsopties, zodat u visueel aantrekkelijke en informatieve diagrammen in uw Word-documenten kunt maken.

### Veelgestelde vragen

#### Q1. Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, wijzigen en converteren in .NET-toepassingen. Het biedt een uitgebreide set API's voor tekstverwerking met documentelementen, waaronder diagrammen, alinea's, tabellen en meer.

#### Vraag 2. Hoe installeer ik Aspose.Words voor .NET?
Om Aspose.Words voor .NET te installeren, kunt u de NuGet-pakketbeheerder in Visual Studio gebruiken om de bibliotheek rechtstreeks in uw project te installeren. Zoek eenvoudigweg naar "Aspose.Words" in de NuGet-pakketbeheerder en installeer het pakket.

#### Q3. Kan ik het uiterlijk van het vlakdiagram aanpassen?
Ja, met Aspose.Words voor .NET kunt u verschillende aspecten van de weergave van het vlakdiagram aanpassen. U kunt eigenschappen wijzigen, zoals de diagramtitel, reekskleur, aslabels en de opmaak van het diagramgebied. De bibliotheek biedt een uitgebreide set API's om de visuele elementen van het diagram te beheren en een aangepast uiterlijk te creëren dat aan uw behoeften voldoet.

#### Q4. Kan ik meerdere reeksen aan het vlakdiagram toevoegen?
Ja, u kunt meerdere reeksen aan het vlakdiagram toevoegen met Aspose.Words voor .NET. Elke reeks vertegenwoordigt een reeks gegevenspunten die in de grafiek zijn uitgezet. U kunt reeksen met verschillende gegevenssets toevoegen en elke reeks afzonderlijk aanpassen, inclusief de naam, gegevenspunten en het uiterlijk.

#### Vraag 5. Kan ik het document met het ingevoegde vlakdiagram in verschillende formaten opslaan?
 Ja, met Aspose.Words voor .NET kunt u het document met het ingevoegde vlakdiagram opslaan in verschillende formaten, zoals DOCX, PDF, HTML en meer. U kunt het gewenste uitvoerformaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan. Het ingevoegde vlakdiagram blijft behouden in het opgeslagen document.

#### Vraag 6. Kan ik de gegevens en het uiterlijk van het vlakdiagram wijzigen nadat ik het heb ingevoegd?
Ja, nadat u het vlakdiagram in het document hebt ingevoegd, kunt u de gegevens en het uiterlijk ervan wijzigen met behulp van de API's van Aspose.Words voor .NET. U kunt de reeksgegevens bijwerken, het diagramtype wijzigen, aseigenschappen aanpassen en opmaakopties toepassen om dynamische en interactieve diagrammen in uw Word-documenten te maken.