---
title: Voeg datum-tijdwaarden toe aan de as van een diagram
linktitle: Voeg datum-tijdwaarden toe aan de as van een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u datum- en tijdwaarden aan de as van een diagram toevoegt met Aspose.Words voor .NET in deze uitgebreide stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-charts/date-time-values-to-axis/
---
## Invoering

Het maken van diagrammen in documenten kan een krachtige manier zijn om gegevens te visualiseren. Bij het omgaan met tijdreeksgegevens is het toevoegen van datum- en tijdwaarden aan de as van een diagram cruciaal voor de duidelijkheid. In deze zelfstudie begeleiden we u bij het toevoegen van datum- en tijdwaarden aan de as van een diagram met behulp van Aspose.Words voor .NET. Deze stapsgewijze handleiding helpt u bij het opzetten van uw omgeving, het schrijven van de code en het begrijpen van elk onderdeel van het proces. Laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Visual Studio of een andere .NET IDE: u hebt een ontwikkelomgeving nodig om uw .NET-code te schrijven en uit te voeren.
2.  Aspose.Words voor .NET: De Aspose.Words voor .NET-bibliotheek moet geïnstalleerd zijn. Je kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
3. Basiskennis van C#: Deze tutorial gaat ervan uit dat je een basiskennis hebt van programmeren in C#.
4.  Een geldige Aspose-licentie: U kunt een tijdelijke licentie verkrijgen via[hier](https://purchase.aspose.com/temporary-license/).

## Naamruimten importeren

Zorg er om te beginnen voor dat de benodigde naamruimten in uw project zijn geïmporteerd. Deze stap is cruciaal voor toegang tot de Aspose.Words-klassen en -methoden.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Stap 1: Stel uw documentenmap in

Eerst moet u de map definiëren waarin uw document zal worden opgeslagen. Dit is belangrijk voor het organiseren van uw bestanden en om ervoor te zorgen dat uw code correct wordt uitgevoerd.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en DocumentBuilder

 Maak vervolgens een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp. Deze objecten helpen u bij het samenstellen en manipuleren van uw document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een diagram in het document in

 Voeg nu een diagram in uw document in met behulp van de`DocumentBuilder` voorwerp. In dit voorbeeld gebruiken we een kolomdiagram, maar u kunt ook andere typen kiezen.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Stap 4: Wis bestaande series

Wis eventuele bestaande series in het diagram om er zeker van te zijn dat u met een schone lei begint. Deze stap is essentieel voor aangepaste gegevens.

```csharp
chart.Series.Clear();
```

## Stap 5: Voeg datum- en tijdwaarden toe aan de reeks

Voeg uw datum- en tijdwaarden toe aan de diagramserie. Deze stap omvat het maken van arrays voor datums en bijbehorende waarden.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Stap 6: Configureer de X-as

Stel de schaal en maatstreepjes voor de X-as in. Dit zorgt ervoor dat uw datums correct en met de juiste tussenpozen worden weergegeven.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Stap 7: Bewaar het document

Sla ten slotte uw document op in de opgegeven map. Met deze stap wordt het proces afgerond en uw document zou nu een diagram moeten bevatten met datum- en tijdwaarden op de X-as.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Conclusie

Het toevoegen van datum- en tijdwaarden aan de as van een diagram in een document is een eenvoudig proces met Aspose.Words voor .NET. Door de stappen in deze zelfstudie te volgen, kunt u duidelijke en informatieve diagrammen maken die tijdreeksgegevens effectief visualiseren. Of u nu rapporten, presentaties of welk document dan ook voorbereidt dat gedetailleerde gegevensrepresentatie vereist, Aspose.Words biedt de tools die u nodig hebt om te slagen.

## Veelgestelde vragen

### Kan ik andere diagramtypen gebruiken met Aspose.Words voor .NET?

Ja, Aspose.Words ondersteunt verschillende diagramtypen, waaronder lijn-, staaf-, cirkel- en meer.

### Hoe kan ik het uiterlijk van mijn diagram aanpassen?

kunt het uiterlijk aanpassen door de eigenschappen van het diagram te openen en stijlen, kleuren en meer in te stellen.

### Is het mogelijk om meerdere reeksen aan een diagram toe te voegen?

 Absoluut! U kunt meerdere series aan uw diagram toevoegen door het telefoonnummer te bellen`Series.Add` methode meerdere keren met verschillende gegevens.

### Wat moet ik doen als ik de kaartgegevens dynamisch moet bijwerken?

U kunt de diagramgegevens dynamisch bijwerken door de reeks- en aseigenschappen programmatisch te manipuleren op basis van uw vereisten.

### Waar kan ik meer gedetailleerde documentatie vinden voor Aspose.Words voor .NET?

 U kunt meer gedetailleerde documentatie vinden[hier](https://reference.aspose.com/words/net/).