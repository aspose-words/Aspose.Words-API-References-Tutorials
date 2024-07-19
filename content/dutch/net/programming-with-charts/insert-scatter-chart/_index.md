---
title: Voeg een spreidingsdiagram in een Word-document in
linktitle: Voeg een spreidingsdiagram in een Word-document in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een spreidingsdiagram invoegt in Word met Aspose.Words voor .NET. Eenvoudige stappen voor het integreren van visuele gegevensrepresentaties in uw documenten.
type: docs
weight: 10
url: /nl/net/programming-with-charts/insert-scatter-chart/
---
## Invoering

In deze zelfstudie leert u hoe u Aspose.Words voor .NET kunt gebruiken om een spreidingsdiagram in uw Word-document in te voegen. Spreidingsdiagrammen zijn krachtige visuele hulpmiddelen die gegevenspunten effectief kunnen weergeven op basis van twee variabelen, waardoor uw documenten aantrekkelijker en informatiever worden.

## Vereisten

Voordat we ingaan op het maken van spreidingsdiagrammen met Aspose.Words voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Installatie van Aspose.Words voor .NET: Download en installeer Aspose.Words voor .NET van[hier](https://releases.aspose.com/words/net/).
   
2. Basiskennis van C#: Bekendheid met de programmeertaal C# en het .NET-framework zal nuttig zijn.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten in uw C#-project importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

Laten we nu het proces van het invoegen van een spreidingsdiagram in uw Word-document met behulp van Aspose.Words voor .NET opsplitsen:

## Stap 1: Initialiseer het document en DocumentBuilder

 Initialiseer eerst een nieuw exemplaar van het`Document` klasse en`DocumentBuilder` klasse om te beginnen met het maken van uw document.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg het spreidingsdiagram in

 Gebruik de`InsertChart` werkwijze van de`DocumentBuilder` class om een spreidingsdiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Stap 3: Voeg gegevensreeksen toe aan het diagram

Voeg nu gegevensreeksen toe aan uw spreidingsdiagram. Dit voorbeeld demonstreert het toevoegen van een reeks met specifieke gegevenspunten.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Stap 4: Sla het document op

 Sla ten slotte het gewijzigde document op de gewenste locatie op met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u een spreidingsdiagram in uw Word-document kunt invoegen met Aspose.Words voor .NET. Spreidingsdiagrammen zijn uitstekende hulpmiddelen voor het visualiseren van gegevensrelaties, en met Aspose.Words kunt u ze moeiteloos in uw documenten integreren om de duidelijkheid en het begrip te vergroten.

## Veelgestelde vragen

### Kan ik het uiterlijk van het spreidingsdiagram aanpassen met Aspose.Words?
Ja, Aspose.Words maakt uitgebreide aanpassing van diagrameigenschappen mogelijk, zoals kleuren, assen en labels.

### Is Aspose.Words compatibel met verschillende versies van Microsoft Word?
Aspose.Words ondersteunt verschillende versies van Microsoft Word, waardoor compatibiliteit tussen platforms wordt gegarandeerd.

### Biedt Aspose.Words ondersteuning voor andere typen diagrammen?
Ja, Aspose.Words ondersteunt een breed scala aan diagramtypen, waaronder staafdiagrammen, lijndiagrammen en cirkeldiagrammen.

### Kan ik gegevens in het spreidingsdiagram programmatisch dynamisch bijwerken?
Absoluut, u kunt diagramgegevens dynamisch bijwerken met behulp van Aspose.Words API-aanroepen.

### Waar kan ik verdere hulp of ondersteuning krijgen voor Aspose.Words?
 Voor verdere hulp kunt u terecht op de[Aspose.Words-ondersteuningsforum](https://forum.aspose.com/c/words/8).