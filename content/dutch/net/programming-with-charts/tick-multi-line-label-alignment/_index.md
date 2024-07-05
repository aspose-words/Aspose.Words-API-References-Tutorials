---
title: Vink Uitlijning van labels met meerdere regels in een diagram aan
linktitle: Vink Uitlijning van labels met meerdere regels in een diagram aan
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u labels met meerdere regels in een diagramas uitlijnt met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/tick-multi-line-label-alignment/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om de uitlijning van labels met meerdere regels in een diagramas in te stellen. De meegeleverde broncode laat zien hoe u een diagram maakt, toegang krijgt tot de as en de uitlijning van het vinkje wijzigt.

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

 Gebruik vervolgens de`InsertChart` werkwijze van de`DocumentBuilder` om een spreidingsdiagram in het document in te voegen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Stap 3: Stel de uitlijning van het vinkje in

 Om de uitlijning van labels met meerdere regels in te stellen, gaat u naar de`AxisX` eigenschap van het diagram en stel de`TickLabelAlignment` eigenschap naar de gewenste uitlijning. In dit voorbeeld stellen we de uitlijning in op`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Stap 4: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Hiermee is de implementatie voltooid van het instellen van de uitlijning van labels met meerdere regels met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Tick Multi Line Label Alignment met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Deze eigenschap heeft alleen effect op labels met meerdere regels.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de uitlijning van meerregelige labels in een diagramas kunt instellen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een spreidingsdiagram invoegen, toegang krijgen tot de diagramas en de uitlijning van het vinkje wijzigen.

Aspose.Words voor .NET biedt krachtige functies voor het manipuleren van diagrammen in Word-documenten. Het aanvinken van labels met meerdere regels is handig wanneer aslabels lange tekst bevatten die moet worden teruggelopen of over meerdere regels moet worden gesplitst. Door de uitlijning van de vinklabels in te stellen, kunt u de horizontale uitlijning van labels met meerdere regels binnen de diagramas bepalen, waardoor een optimale presentatie en leesbaarheid wordt gegarandeerd.

Door de uitlijning van labels met meerdere regels aan te passen, kunt u het uiterlijk van uw diagram verfijnen, vooral als u te maken heeft met lange of complexe labels. Door de labels rechts, links, gecentreerd of uitgelijnd uit te lijnen, kunt u een evenwichtige en visueel aantrekkelijke opstelling van vinkjes langs de as bereiken.

Met Aspose.Words voor .NET kunt u eenvoudig de uitlijningseigenschap van de maatstreeplabels van een grafiekas openen en wijzigen, waardoor u volledige controle krijgt over het uiterlijk en de indeling van de maatstreeplabels in uw Word-documentdiagrammen.

### Veelgestelde vragen

#### Q1. Wat zijn vinklabels met meerdere regels in een diagramas?
Aangevinkte labels met meerdere regels in een diagramas verwijzen naar de aslabels die zich over meerdere regels uitstrekken wanneer de labeltekst lang is of moet worden teruggelopen om in de beschikbare ruimte te passen. In plaats van de labeltekst af te korten of visuele rommel te veroorzaken, splitst de diagramas de labels automatisch in meerdere regels om de leesbaarheid te garanderen. Aanvinklabels met meerdere regels zijn vooral handig als u te maken heeft met lange categorie- of waardelabels in diagrammen.

#### Vraag 2. Kan ik de uitlijning van maatstreeplabels in een diagramas aanpassen?
 Ja, u kunt de uitlijning van maatstreeplabels in een diagramas aanpassen met Aspose.Words voor .NET. Door toegang te krijgen tot de`TickLabelAlignment` eigendom van de`ChartAxis` object, kunt u de gewenste uitlijning voor de vinklabels instellen. De uitlijningsopties omvatten links, rechts, gecentreerd of uitgevuld. Door de uitlijning aan te passen, kunt u de horizontale positionering van maatstreeplabels langs de kaartas bepalen, waardoor een goede leesbaarheid en visuele presentatie wordt gegarandeerd.

#### Q3. Wanneer moet ik overwegen de uitlijning van het maatstreepje in een diagramas te wijzigen?
Het wijzigen van de uitlijning van de vinklabels in een grafiekas is handig als u lange labels of labels met meerdere regels hebt die een optimale presentatie en leesbaarheid vereisen. Door de uitlijning aan te passen, kunt u ervoor zorgen dat de labels op de juiste manier worden uitgelijnd en op afstand van elkaar staan, zodat overlapping of afkapping wordt voorkomen. Overweeg om de uitlijning van de vinklabels te wijzigen als u werkt met diagrammen met lange categorienamen, uitgebreide waardelabels of andere scenario's waarin de standaarduitlijning niet het gewenste visuele uiterlijk oplevert.

#### Q4. Heeft de uitlijning van vinklabels invloed op labels met één regel in een diagramas?
Nee, de eigenschap voor het uitlijnen van vinklabels heeft geen invloed op labels met één regel in een diagramas. Het is speciaal ontworpen voor etiketten met meerdere regels die ingepakt of gesplitst moeten worden. Labels met één regel worden uitgelijnd op basis van de standaarduitlijningsinstellingen van de diagramas. De eigenschap Uitlijning van vinklabels is alleen van toepassing op labels die meerdere regels beslaan, zodat u de uitlijning van elke regel binnen het label met meerdere regels kunt bepalen.

#### Vraag 5. Kan ik maatstreeplabels anders uitlijnen voor de X-as en de Y-as in een diagram?
 Ja, u kunt maatstreeplabels anders uitlijnen voor de X-as en de Y-as in een diagram met Aspose.Words voor .NET. De eigenschap voor het uitlijnen van vinklabels is specifiek voor elke diagramas. Door toegang te krijgen tot de overeenkomstige`ChartAxis` object voor de X-as of Y-as, kunt u de uitlijning van het vinkje op verschillende waarden instellen. Dit biedt u de flexibiliteit om maatstreeplabels verschillend uit te lijnen op basis van uw specifieke vereisten voor elke as in het diagram.