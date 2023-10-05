---
title: Utilisation de graphiques dans Aspose.Words pour Java
linktitle: Utiliser des graphiques
second_title: API de traitement de documents Java Aspose.Words
description: Découvrez comment créer et personnaliser des graphiques dans Aspose.Words pour Java. Explorez les types de graphiques, le formatage et les propriétés des axes pour la visualisation des données.
type: docs
weight: 12
url: /fr/java/document-conversion-and-export/using-charts/
---

## Introduction à l'utilisation de graphiques dans Aspose.Words pour Java

Dans ce didacticiel, nous verrons comment utiliser des graphiques à l'aide d'Aspose.Words pour Java. Vous apprendrez à créer différents types de graphiques, à personnaliser les propriétés des axes, à formater les étiquettes de données, etc. Allons-y !

## Création d'un graphique linéaire

Pour créer un graphique linéaire, utilisez le code suivant :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// Supprimez la série générée par défaut.
chart.getSeries().clear();

// Ajout d'une série avec des données et des étiquettes de données.
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// Ou liez le code de format à une cellule source.
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Création d'autres types de graphiques

Vous pouvez créer différents types de graphiques comme des colonnes, des aires, des bulles, des nuages de points, etc. en utilisant des techniques similaires. Voici un exemple d'insertion d'un histogramme simple :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Supprimez la série générée par défaut.
chart.getSeries().clear();

// Création de catégories et ajout de données.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Personnalisation des propriétés de l'axe

Vous pouvez personnaliser les propriétés de l'axe, telles que la modification du type d'axe, la définition de graduations, le formatage des étiquettes, etc. Voici un exemple de définition des propriétés de l'axe XY :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// Effacez la série par défaut et ajoutez vos données.

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// Changez l'axe X pour qu'il soit une catégorie au lieu d'une date.
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //Mesuré en unités d'affichage de l'axe Y (centaines).
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

## Formatage des étiquettes de données

Vous pouvez formater les étiquettes de données avec différents formats de nombres. Voici un exemple :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Effacez la série par défaut et ajoutez vos données.

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Personnalisations supplémentaires des graphiques

Vous pouvez personnaliser davantage vos graphiques en ajustant les limites, les unités d'intervalle entre les étiquettes, en masquant les axes du graphique, etc. Explorez les extraits de code fournis pour en savoir plus sur ces options.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment utiliser des graphiques à l'aide d'Aspose.Words pour Java. Vous avez appris à créer différents types de graphiques, à personnaliser les propriétés des axes, à formater les étiquettes de données, etc. Aspose.Words for Java fournit des outils puissants pour ajouter des représentations visuelles de données à vos documents, améliorant ainsi la façon dont vous présentez les informations.

## FAQ

### Comment puis-je ajouter plusieurs séries à un graphique ?

 Vous pouvez ajouter plusieurs séries à un graphique à l'aide de l'outil`chart.getSeries().add()` méthode. Assurez-vous de spécifier le nom de la série, les catégories et les valeurs des données.

### Comment puis-je formater des étiquettes de données avec des formats numériques personnalisés ?

Vous pouvez formater les étiquettes de données en accédant à`DataLabels` propriétés d'une série et définition du code de format souhaité à l'aide`getNumberFormat().setFormatCode()`.

### Comment personnaliser les propriétés des axes dans un graphique ?

 Vous pouvez personnaliser les propriétés des axes telles que le type, les graduations, les étiquettes, etc. en accédant à l'onglet`ChartAxis` des propriétés comme`setCategoryType()`, `setCrosses()` , et`setMajorTickMark()`.

### Comment puis-je créer d’autres types de graphiques comme des graphiques en nuages de points ou en aires ?

 Vous pouvez créer différents types de graphiques en spécifiant le`ChartType` lors de l'insertion du graphique à l'aide`builder.insertChart(ChartType.TYPE, width, height)`.

### Comment puis-je masquer un axe du graphique ?

 Vous pouvez masquer un axe du graphique en définissant le`setHidden(true)` propriété de l’axe.