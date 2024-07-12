---
title: Stel standaardopties in voor gegevenslabels in een diagram
linktitle: Stel standaardopties in voor gegevenslabels in een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u standaardopties voor gegevenslabels in een diagram instelt met Aspose.Words voor .NET. Volg onze stapsgewijze handleiding om moeiteloos grafieken te maken en aan te passen.
type: docs
weight: 10
url: /nl/net/programming-with-charts/default-options-for-data-labels/
---
## Invoering

Hallo daar! Heeft u zin om in de wereld van documentautomatisering te duiken? Vandaag gaan we onderzoeken hoe we Aspose.Words voor .NET kunnen gebruiken om programmatisch verbluffende documenten te maken. Aspose.Words is een krachtige bibliotheek waarmee u gemakkelijk Word-documenten kunt manipuleren, en in deze zelfstudie concentreren we ons op het instellen van standaardopties voor gegevenslabels in een diagram. Of u nu een doorgewinterde ontwikkelaar of een nieuweling bent, deze handleiding begeleidt u bij elke stap, zodat u in een mum van tijd aan de slag kunt.

## Vereisten

Voordat we beginnen, zorgen we ervoor dat u alles heeft wat u nodig heeft om deze tutorial te volgen. Hier is een korte checklist:

- Visual Studio of een andere .NET-compatibele IDE: hier schrijft en voert u uw code uit.
-  Aspose.Words voor .NET: dat kan[download de nieuwste versie](https://releases.aspose.com/words/net/) en installeer het in uw project.
- Basiskennis van programmeren in C#: Hoewel deze handleiding beginnersvriendelijk is, kan een beetje bekendheid met C# nuttig zijn.
- .NET Framework geïnstalleerd: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.
-  Een tijdelijke licentie voor Aspose.Woorden: koop er een[hier](https://purchase.aspose.com/temporary-license/) om de volledige functionaliteit te ontgrendelen.

Zodra u aan deze vereisten voldoet, zijn we klaar om aan de slag te gaan!

## Naamruimten importeren

Laten we eerst ons project opzetten en de benodigde naamruimten importeren. Deze naamruimten zijn cruciaal voor toegang tot de Aspose.Words-functionaliteit.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Stap 1: Maak een nieuw document


 De reis begint met het maken van een nieuw document en het initialiseren van een`DocumentBuilder` . De`DocumentBuilder` class biedt een reeks methoden om de documentinhoud eenvoudig te manipuleren.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Maak een nieuw document
Document doc = new Document();

// Initialiseer DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Uitleg

 In deze stap hebben we het document en de builder ingesteld die we gaan gebruiken om onze inhoud in te voegen en op te maken. De`dataDir` variabele bevat het pad waar we ons definitieve document zullen opslaan.

## Stap 2: Voeg een diagram in

 Vervolgens voegen we een cirkeldiagram toe aan ons document. De`InsertChart` werkwijze van de`DocumentBuilder` klasse maakt dit supergemakkelijk.

```csharp
// Voeg een cirkeldiagram in
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Toegang tot het diagramobject
Chart chart = shape.Chart;
```

### Uitleg

Hier voegen we een cirkeldiagram in ons document in. De`InsertChart` methode vereist het diagramtype, de breedte en de hoogte als parameters. Nadat we het diagram hebben ingevoegd, hebben we toegang tot het diagramobject om het verder te manipuleren.

## Stap 3: Pas de grafiekreeks aan

Nu zullen we alle bestaande reeksen in het diagram wissen en onze aangepaste reeksen toevoegen. Deze reeks vertegenwoordigt onze gegevenspunten.

```csharp
// Bestaande kaartreeksen wissen
chart.Series.Clear();

// Voeg nieuwe series toe aan het diagram
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Uitleg

In deze stap zorgen we ervoor dat ons diagram leeg is door alle bestaande reeksen te wissen. Vervolgens voegen we een nieuwe reeks toe met aangepaste categorieën en waarden, die in ons cirkeldiagram worden weergegeven.

## Stap 4: Stel standaardopties voor gegevenslabels in

Gegevenslabels zijn van cruciaal belang om uw diagram informatief te maken. We stellen opties in om het percentage en de waarde weer te geven en het scheidingsteken aan te passen.

```csharp
// Toegang tot de verzameling gegevenslabels
ChartDataLabelCollection labels = series.DataLabels;

// Opties voor gegevenslabels instellen
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Uitleg

 Hier hebben we toegang tot de`DataLabels`eigendom van onze serie om het uiterlijk en de informatie die op elk gegevenslabel wordt weergegeven, aan te passen. We hebben ervoor gekozen om zowel het percentage als de waarde weer te geven, aanhaallijnen te verbergen en een aangepast scheidingsteken in te stellen.

## Stap 5: Bewaar het document

Ten slotte slaan we ons document op in de opgegeven map. Deze stap zorgt ervoor dat al onze wijzigingen naar een bestand worden geschreven.

```csharp
// Bewaar het document
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Uitleg

 In deze laatste stap slaan we ons document op met behulp van de`Save` methode. Het document wordt opgeslagen in de map die is opgegeven door`dataDir`, met de naam "WorkingWithCharts.DefaultOptionsForDataLabels.docx".

## Conclusie

En daar heb je het! U hebt met succes een Word-document met een aangepast cirkeldiagram gemaakt met behulp van Aspose.Words voor .NET. Deze krachtige bibliotheek maakt het eenvoudig om het maken en manipuleren van documenten te automatiseren, waardoor u tijd en moeite bespaart. Of u nu rapporten, facturen of een ander type document genereert, Aspose.Words heeft de oplossing voor u.

 Ontdek gerust de[Aspose.Words-documentatie](https://reference.aspose.com/words/net/) voor meer functies en voorbeelden. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik Aspose.Words gratis gebruiken?
Je kunt Aspose.Words gratis gebruiken met een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) of verken de functies ervan met behulp van de[gratis proefperiode](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning voor Aspose.Words?
 U kunt ondersteuning krijgen via de[Aspose.Words-ondersteuningsforum](https://forum.aspose.com/c/words/8).

### Kan ik andere typen diagrammen toevoegen?
 Ja, Aspose.Words ondersteunt verschillende diagramtypen, zoals staaf-, lijn- en kolomdiagrammen. Controleer de[documentatie](https://reference.aspose.com/words/net/) voor meer details.

### Is Aspose.Words compatibel met .NET Core?
 Ja, Aspose.Words is compatibel met .NET Core. Meer informatie vindt u in de[documentatie](https://reference.aspose.com/words/net/).

### Hoe kan ik een licentie kopen voor Aspose.Words?
 U kunt een licentie aanschaffen bij de[Aspose-winkel](https://purchase.aspose.com/buy).

