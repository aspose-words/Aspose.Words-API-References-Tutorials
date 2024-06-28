---
title: Formatteer het aantal gegevenslabels in een grafiek
linktitle: Formatteer het aantal gegevenslabels in een grafiek
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het aantal gegevenslabels in een diagram kunt opmaken met Aspose.Words voor .NET. Pas eenvoudig getalnotaties voor gegevenslabels aan.
type: docs
weight: 10
url: /nl/net/programming-with-charts/format-number-of-data-label/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om het aantal gegevenslabels in een diagram op te maken. De meegeleverde broncode laat zien hoe u een diagram maakt, reeksgegevens toevoegt en de getalnotatie van gegevenslabels aanpast.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden door NuGet-pakketbeheer te gebruiken om het te installeren.
- Een documentmappad waar het uitvoerdocument wordt opgeslagen.

## Stap 2: Maak een nieuw document en voeg een diagram in.

 Maak een nieuwe`Document` voorwerp en een`DocumentBuilder` om het document op te bouwen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Voeg vervolgens een diagram in het document in met behulp van de`InsertChart` werkwijze van de`DocumentBuilder`. In dit voorbeeld voegen we een lijndiagram in.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Stap 3: Voeg seriegegevens toe aan het diagram

Voeg seriegegevens toe aan het diagram. In dit voorbeeld voegen we drie categorieën en de bijbehorende waarden toe.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Stap 4: Pas het getalformaat van gegevenslabels aan

 Om het aantal gegevenslabels op te maken, gaat u naar het bestand`DataLabels` collectie die bij de serie hoort.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In dit voorbeeld stellen we voor elk gegevenslabel verschillende getalnotaties in. Het eerste gegevenslabel is opgemaakt als valuta, het tweede als datum en het derde als percentage.

## Stap 5: Sla het document op

 Sla het document ten slotte op in de opgegeven map met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Hiermee is de implementatie voltooid van het opmaken van het aantal gegevenslabels in een diagram met Aspose.Words voor .NET.

### Voorbeeldbroncode voor formaatnummer van gegevenslabel met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Verwijder standaard gegenereerde reeksen.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Of u kunt de opmaakcode instellen zodat deze aan een broncel wordt gekoppeld,
	//In dit geval wordt NumberFormat opnieuw ingesteld op algemeen en overgenomen van een broncel.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u het aantal gegevenslabels in een diagram kunt opmaken met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u een diagram maken, seriegegevens toevoegen en de getalnotatie van gegevenslabels aanpassen aan uw vereisten.

 Aspose.Words voor .NET biedt een uitgebreide API voor woordenverwerking met diagrammen in Word-documenten, waardoor u verschillende aspecten van het diagram kunt manipuleren, inclusief gegevenslabels. Door toegang te krijgen tot de`DataLabels` verzameling die aan een reeks is gekoppeld, kunt u de getalnotatie van individuele gegevenslabels aanpassen.

Met de API kunt u de weergave van waarden beheren, verschillende getalnotaties voor elk gegevenslabel instellen en het getalformaat aan een broncel koppelen. Dankzij deze flexibiliteit kunt u numerieke gegevens in diagrammen presenteren met de gewenste opmaak, zoals valutasymbolen, datumnotaties en percentagewaarden.

Door Aspose.Words voor .NET te gebruiken, kunt u krachtige grafiekmogelijkheden in uw .NET-toepassingen integreren en professioneel ogende documenten genereren met volledig opgemaakte grafieken en gegevenslabels.

### Veelgestelde vragen

#### Q1. Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een veelzijdige bibliotheek voor documentverwerking waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en opslaan in .NET-toepassingen. Het biedt een breed scala aan functies voor tekstverwerking met documentelementen, waaronder grafieken en gegevenslabels.

#### Vraag 2. Hoe kan ik Aspose.Words voor .NET installeren?
kunt Aspose.Words voor .NET installeren door het te downloaden met behulp van NuGet-pakketbeheer in Visual Studio. Zoek eenvoudigweg naar "Apose.Words" in de NuGet-pakketbeheerder en installeer het in uw project.

#### Q3. Kan ik andere aspecten van het diagram opmaken met Aspose.Words voor .NET?
Ja, Aspose.Words voor .NET biedt uitgebreide mogelijkheden voor het opmaken van verschillende aspecten van een diagram. Naast gegevenslabels kunt u het diagramtype, reeksgegevens, aseigenschappen, legenda, titel, plotgebied en vele andere elementen van het diagram aanpassen. De API biedt fijnmazige controle over het uiterlijk en de opmaak van diagrammen.

#### Q4. Kan ik verschillende getalformaten toepassen op verschillende gegevenslabels in dezelfde serie?
Ja, met Aspose.Words voor .NET kunt u verschillende getalformaten toepassen op individuele gegevenslabels binnen dezelfde reeks. Door toegang te krijgen tot de`DataLabels` collectie die aan een serie is gekoppeld, kunt u de`FormatCode` eigenschap van elk gegevenslabel om het gewenste getalformaat op te geven. Hierdoor kunt u numerieke waarden in verschillende formaten binnen hetzelfde diagram presenteren.

#### Vraag 5. Kan ik aangepaste getalnotaties gebruiken voor gegevenslabels?
 Ja, Aspose.Words voor .NET ondersteunt aangepaste getalnotaties voor gegevenslabels. U kunt het gewenste getalformaat opgeven door de`FormatCode` eigenschap van een gegevenslabel naar een aangepaste formaatcode. Dit geeft u de flexibiliteit om een breed scala aan getalnotaties toe te passen, zoals valutasymbolen, datumnotaties, percentagewaarden en meer.

#### Vraag 6. Kan ik het diagram met opgemaakte gegevenslabels in verschillende formaten opslaan?
Ja, met Aspose.Words voor .NET kunt u het document met het diagram opslaan met opgemaakte gegevenslabels in verschillende formaten, zoals DOCX, PDF, HTML en meer. U kunt het juiste formaat kiezen op basis van uw vereisten en de`Save` werkwijze van de`Document` object om het document op te slaan. De opgemaakte gegevenslabels blijven behouden in het opgeslagen document.