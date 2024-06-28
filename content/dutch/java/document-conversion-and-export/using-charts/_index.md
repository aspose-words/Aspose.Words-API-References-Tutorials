---
title: Grafieken gebruiken in Aspose.Words voor Java
linktitle: Grafieken gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u diagrammen kunt maken en aanpassen in Aspose.Words voor Java. Ontdek diagramtypen, opmaak en aseigenschappen voor gegevensvisualisatie.
type: docs
weight: 12
url: /nl/java/document-conversion-and-export/using-charts/
---

## Inleiding tot het gebruik van diagrammen in Aspose.Words voor Java

In deze zelfstudie onderzoeken we hoe u met diagrammen kunt werken met Aspose.Words voor Java. U leert hoe u verschillende soorten diagrammen maakt, aseigenschappen aanpast, gegevenslabels opmaakt en meer. Laten we erin duiken!

## Een lijndiagram maken

Gebruik de volgende code om een lijndiagram te maken:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// Verwijder standaard gegenereerde reeksen.
chart.getSeries().clear();

// Een reeks met gegevens en gegevenslabels toevoegen.
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// Of koppel formaatcode aan een broncel.
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Andere soorten grafieken maken

Met vergelijkbare technieken kunt u verschillende typen diagrammen maken, zoals kolom-, vlak-, bel-, spreidingsdiagrammen en meer. Hier is een voorbeeld van het invoegen van een eenvoudig kolomdiagram:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Verwijder standaard gegenereerde reeksen.
chart.getSeries().clear();

// Categorieën maken en gegevens toevoegen.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Aseigenschappen aanpassen

U kunt aseigenschappen aanpassen, zoals het wijzigen van het astype, het instellen van maatstreepjes, het opmaken van labels en meer. Hier is een voorbeeld van het definiëren van XY-aseigenschappen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// Wis de standaardreeksen en voeg uw gegevens toe.

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// Wijzig de X-as zodat deze een categorie is in plaats van een datum.
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //Gemeten in weergave-eenheden van de Y-as (honderden).
xAxis.setReverseOrder(true);
xAxis.setMajorTickMark(AxisTickMark.CROSS);
xAxis.setMinorTickMark(AxisTickMark.OUTSIDE);
xAxis.setTickLabelOffset(200);

yAxis.setTickLabelPosition(AxisTickLabelPosition.HIGH);
yAxis.setMajorUnit(100.0);
yAxis.setMinorUnit(50.0);
yAxis.getDisplayUnit().setUnit(AxisBuiltInUnit.HUNDREDS);
yAxis.getScaling().setMinimum(new AxisBound(100.0));
yAxis.getScaling().setMaximum(new AxisBound(700.0));

doc.save("Your Directory Path" + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Gegevenslabels opmaken

U kunt gegevenslabels opmaken met verschillende getalnotaties. Hier is een voorbeeld:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Wis de standaardreeksen en voeg uw gegevens toe.

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Aanvullende kaartaanpassingen

U kunt uw diagrammen verder aanpassen door grenzen, intervaleenheden tussen labels aan te passen, diagramassen te verbergen en meer. Bekijk de meegeleverde codefragmenten voor meer informatie over deze opties.

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u met diagrammen kunt werken met Aspose.Words voor Java. U hebt geleerd hoe u verschillende soorten diagrammen kunt maken, aseigenschappen kunt aanpassen, gegevenslabels kunt opmaken en meer. Aspose.Words voor Java biedt krachtige hulpmiddelen voor het toevoegen van visuele representaties van gegevens aan uw documenten, waardoor de manier waarop u informatie presenteert wordt verbeterd.

## Veelgestelde vragen

### Hoe kan ik meerdere reeksen aan een diagram toevoegen?

 U kunt meerdere reeksen aan een diagram toevoegen met behulp van de`chart.getSeries().add()` methode. Zorg ervoor dat u de serienaam, categorieën en gegevenswaarden opgeeft.

### Hoe kan ik gegevenslabels opmaken met aangepaste getalnotaties?

 kunt gegevenslabels opmaken door naar het bestand`DataLabels` eigenschappen van een serie en het instellen van de gewenste formaatcode met behulp van`getNumberFormat().setFormatCode()`.

### Hoe pas ik aseigenschappen in een diagram aan?

 U kunt aseigenschappen, zoals type, maatstreepjes, labels en meer, aanpassen door naar het`ChartAxis` eigenschappen zoals`setCategoryType()`, `setCrosses()` , En`setMajorTickMark()`.

### Hoe kan ik andere typen diagrammen maken, zoals spreidings- of vlakdiagrammen?

 U kunt verschillende diagramtypen maken door de juiste op te geven`ChartType` bij het invoegen van het diagram met behulp van`builder.insertChart(ChartType.TYPE, width, height)`.

### Hoe kan ik een diagramas verbergen?

 U kunt een diagramas verbergen door de`setHidden(true)` eigenschap van de as.