---
title: Formatage des tableaux et des styles de tableau dans Aspose.Words pour Java
linktitle: Formatage des tableaux et des styles de tableau
second_title: API de traitement de documents Java Aspose.Words
description: Découvrez comment formater des tableaux et appliquer des styles de tableau dans Aspose.Words pour Java. Explorez des guides étape par étape avec le code source pour un formatage efficace des tableaux. Améliorez la mise en page de votre document avec Aspose.Words.
type: docs
weight: 17
url: /fr/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Introduction au formatage des tableaux et des styles de tableaux dans Aspose.Words pour Java

Les tableaux jouent un rôle crucial dans la structuration et l’organisation des informations dans les documents. Aspose.Words for Java fournit des fonctionnalités puissantes pour formater les tableaux et appliquer des styles de tableau afin d'améliorer l'attrait visuel de vos documents. Dans ce guide étape par étape, nous explorerons divers aspects du formatage des tableaux et de l'application de styles de tableau à l'aide d'Aspose.Words pour Java.

## Conditions préalables

Avant d'entrer dans les détails, assurez-vous que la bibliothèque Aspose.Words for Java est intégrée à votre projet. Vous pouvez le télécharger sur le site Aspose :[Télécharger Aspose.Words pour Java](https://releases.aspose.com/words/java/).

## Obtenir la distance entre le tableau et le texte environnant

Pour commencer, explorons comment récupérer la distance entre un tableau et le texte environnant dans un document.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Appliquer une bordure de contour à un tableau

Vous pouvez aligner un tableau au centre de la page, effacer les bordures existantes et définir une bordure de contour personnalisée avec ce code :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Construire un tableau avec des bordures

Cet extrait de code montre comment créer un tableau et définir des bordures pour le tableau et ses cellules :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Modifier le formatage des lignes

Découvrez comment modifier le formatage d'une ligne spécifique dans un tableau :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Appliquer le formatage des lignes

Cet exemple montre comment appliquer une mise en forme à une ligne entière d'un tableau :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Définir le remplissage des cellules

Découvrez comment définir le remplissage de cellules individuelles dans un tableau :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Modifier le formatage des cellules

Découvrez comment modifier la mise en forme d'une cellule spécifique au sein d'un tableau :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formater le tableau et la cellule avec des bordures différentes

Découvrez comment définir différentes bordures pour des cellules individuelles dans un tableau :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Définir les bordures du tableau
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Définir l'ombrage des cellules pour des cellules individuelles
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Ajouter du contenu aux cellules
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Effacer le formatage des cellules pour la ligne suivante
builder.getCellFormat().clearFormatting();
// Créez des bordures plus grandes pour la première cellule de cette ligne
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Définir le titre et la description du tableau

Ajoutez un titre et une description à votre tableau :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Étape 10 : Autoriser l'espacement des cellules

Autoriser l'espacement des cellules et définir sa valeur pour un tableau :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Étape 11 : Construire une table avec style

Créez un tableau avec un style prédéfini :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Étape 12 : Développez le formatage des cellules et des lignes à partir du style

Découvrez comment développer les styles de tableau pour appliquer une mise en forme aux cellules et aux lignes :

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Étape 13 : Créer un style de tableau

Créez un style de tableau personnalisé avec une mise en forme spécifique :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Étape 14 : Définir la mise en forme conditionnelle

Appliquez une mise en forme conditionnelle aux lignes d'un tableau :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Étape 15 : Définir le formatage de TableCell

Définissez une mise en forme spécifique pour les cellules individuelles :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Étape 16 : Définir le formatage de TableRow

Appliquez une mise en forme à des lignes entières d'un tableau :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Conclusion

Aspose.Words for Java vous permet de formater des tableaux et d'appliquer des styles de tableau avec précision. De la modification du formatage de cellules individuelles à la création de styles de tableau personnalisés, vous disposez des outils nécessaires pour rendre vos documents visuellement attrayants et organisés.

## FAQ

### Comment télécharger Aspose.Words pour Java ?

 Vous pouvez télécharger Aspose.Words pour Java à partir du site Web Aspose :[Télécharger Aspose.Words pour Java](https://releases.aspose.com/words/java/).

### Puis-je appliquer des bordures différentes à des cellules individuelles dans un tableau ?

Oui, vous pouvez définir différentes bordures pour les cellules individuelles d'un tableau à l'aide d'Aspose.Words for Java, comme démontré dans ce guide.

### Quel est le but de définir un titre et une description de tableau ?

La définition d'un titre et d'une description de tableau améliore l'accessibilité et l'organisation de votre document, permettant ainsi aux lecteurs et aux technologies d'assistance de comprendre plus facilement le contenu.

### Comment puis-je appliquer une mise en forme conditionnelle à des lignes spécifiques d’un tableau ?

Vous pouvez appliquer une mise en forme conditionnelle à des lignes spécifiques d'un tableau en définissant des styles de tableau personnalisés avec des règles de mise en forme conditionnelle, comme indiqué dans ce guide.

### Où puis-je trouver plus de documentation et de ressources pour Aspose.Words pour Java ?

 Pour une documentation complète et des ressources supplémentaires, veuillez consulter la documentation Aspose.Words pour Java :[Documentation Aspose.Words pour Java](https://reference.aspose.com/words/java/).