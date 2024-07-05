---
title: Getalnotatie voor as in een diagram
linktitle: Getalnotatie voor as in een diagram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de getalnotatie voor een as in een diagram instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-charts/number-format-for-axis/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om de getalnotatie voor een as in een diagram in te stellen. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en de aslabels opmaakt.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Stap 4: Formatteer de aslabels

 Om de getalnotatie voor de Y-aslabels in te stellen, gaat u naar de`AxisY` eigenschap van het diagram en stel de`NumberFormat.FormatCode` eigenschap naar het gewenste formaat. In dit voorbeeld stellen we de notatie in op "#,##0" om getallen met scheidingstekens voor duizendtallen weer te geven.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Stap 5: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Hiermee is de implementatie voltooid van het instellen van het getalformaat voor de as met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Number Format For Axis met Aspose.Words voor .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de getalnotatie voor een as in een diagram kunt instellen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een nieuw document maken, een kolomdiagram invoegen, reeksgegevens toevoegen en de aslabels opmaken om getallen in een specifiek formaat weer te geven.

Aspose.Words voor .NET biedt krachtige functies om de weergave van diagrammen in Word-documenten aan te passen. Door de getalnotatie voor de aslabels in te stellen, kunt u bepalen hoe getallen worden weergegeven, inclusief opties zoals decimalen, scheidingstekens voor duizendtallen, valutasymbolen en meer. Hierdoor kunt u numerieke gegevens op een duidelijke en betekenisvolle manier presenteren.

Met Aspose.Words voor .NET heeft u de flexibiliteit om verschillende aspecten van het diagram op te maken, inclusief de aslabels. Door het getalformaat voor de as in te stellen, kunt u de consistentie garanderen en de leesbaarheid van het diagram verbeteren, waardoor het voor gebruikers gemakkelijker wordt om de weergegeven waarden te interpreteren.

### Veelgestelde vragen

#### Q1. Wat is de getalnotatie voor een as in een diagram?
De getalnotatie voor een as in een diagram verwijst naar de opmaak die wordt toegepast op de numerieke waarden die op de as worden weergegeven. Hiermee kunt u bepalen hoe getallen worden gepresenteerd, inclusief opties zoals decimalen, scheidingstekens voor duizendtallen, valutasymbolen, procenttekens en meer. Door de getalnotatie in te stellen, kunt u de weergave van numerieke gegevens in het diagram aanpassen aan uw specifieke vereisten.

#### Vraag 2. Hoe kan ik het getalformaat voor de aslabels instellen?
 Om de getalnotatie voor de aslabels in een diagram in te stellen met behulp van Aspose.Words voor .NET, kunt u toegang krijgen tot de`AxisY` eigenschap van het diagram en stel de`NumberFormat.FormatCode`eigenschap naar de gewenste formaatcode. De opmaakcode volgt de syntaxis van standaard numerieke opmaakpatronen en bepaalt hoe de getallen worden weergegeven. U kunt bijvoorbeeld "#,##0.00" gebruiken om getallen met twee decimalen en scheidingstekens voor duizendtallen weer te geven.

#### Q3. Kan ik verschillende getalnotaties instellen voor de X-as- en Y-aslabels?
Ja, u kunt verschillende getalnotaties instellen voor de X-as- en Y-aslabels met Aspose.Words voor .NET. Toegang tot de betreffende as (`AxisX` voor X-as of`AxisY` voor Y-as) van het diagram en wijzig de`NumberFormat.FormatCode` eigenschap afzonderlijk voor elke as. Hierdoor kunt u op elke as verschillende nummerformaten toepassen op de labels, afhankelijk van uw specifieke vereisten.

#### Q4. Wat zijn enkele veelgebruikte getalnotatiecodes die ik kan gebruiken?
Aspose.Words voor .NET ondersteunt een breed scala aan getalnotatiecodes die u kunt gebruiken om de aslabels in een diagram op te maken. Enkele veel voorkomende formaatcodes zijn:

- `0` of`#` - Geeft het getal weer zonder decimalen.
- `0.00` of`#.00` - Geeft het getal weer met twee decimalen.
- `#,##0` Geeft het getal weer met scheidingstekens voor duizendtallen.
- `"€"0.00` - Geeft het getal weer met het euro-valutasymbool en twee decimalen.
- `"%"0` - Geeft het getal weer als een percentage.

 Meer informatie over het nummer vindt u[formaatcodes](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) in API-referentie van Aspose.Words voor .NET.

#### Vraag 5. Kan ik andere eigenschappen van de aslabels aanpassen?
Ja, Aspose.Words voor .NET biedt een breed scala aan eigenschappen om het uiterlijk en het gedrag van aslabels aan te passen. Naast de getalnotatie kunt u eigenschappen wijzigen, zoals lettertype, grootte, kleur, richting, uitlijning en meer. Hierdoor kunt u de aslabels volledig aanpassen aan uw gewenste stijl- en presentatievereisten.