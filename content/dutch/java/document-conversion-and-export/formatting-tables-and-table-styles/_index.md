---
title: Tabellen en tabelstijlen opmaken in Aspose.Words voor Java
linktitle: Tabellen en tabelstijlen opmaken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u tabellen opmaakt en tabelstijlen toepast in Aspose.Words voor Java. Ontdek stapsgewijze handleidingen met broncode voor effectieve tabelopmaak. Verbeter uw documentlay-out met Aspose.Words.
type: docs
weight: 17
url: /nl/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Inleiding tot het opmaken van tabellen en tabelstijlen in Aspose.Words voor Java

Tabellen spelen een cruciale rol bij het structureren en organiseren van informatie in documenten. Aspose.Words voor Java biedt krachtige functies voor het opmaken van tabellen en het toepassen van tabelstijlen om de visuele aantrekkingskracht van uw documenten te vergroten. In deze stapsgewijze handleiding verkennen we verschillende aspecten van het opmaken van tabellen en het toepassen van tabelstijlen met Aspose.Words voor Java.

## Vereisten

Voordat we ingaan op de details, moet u ervoor zorgen dat de Aspose.Words voor Java-bibliotheek in uw project is geïntegreerd. U kunt het downloaden van de Aspose-website:[Download Aspose.Words voor Java](https://releases.aspose.com/words/java/).

## Verkrijg de afstand tussen de tabel en de omringende tekst

Laten we om te beginnen eens kijken hoe we de afstand tussen een tabel en de omringende tekst in een document kunnen achterhalen.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Omtrekrand toepassen op een tabel

Met deze code kunt u een tabel uitlijnen op het midden van de pagina, bestaande randen verwijderen en een aangepaste omtrekrand instellen:

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

## Bouw een tafel met randen

Dit codefragment laat zien hoe u een tabel maakt en randen instelt voor zowel de tabel als de cellen:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Rijopmaak wijzigen

Leer hoe u de opmaak van een specifieke rij in een tabel kunt wijzigen:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Rijopmaak toepassen

Dit voorbeeld laat zien hoe u opmaak toepast op een hele rij in een tabel:

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

## Celopvulling instellen

Ontdek hoe u de opvulling voor individuele cellen in een tabel kunt instellen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Wijzig celopmaak

Ontdek hoe u de opmaak van een specifieke cel in een tabel kunt wijzigen:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatteer tabel en cel met verschillende randen

Leer hoe u verschillende randen instelt voor individuele cellen in een tabel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Stel de tafelranden in
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Stel celarcering in voor individuele cellen
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Voeg inhoud toe aan de cellen
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Wis de celopmaak voor de volgende rij
builder.getCellFormat().clearFormatting();
// Maak grotere randen voor de eerste cel van deze rij
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Stel de tabeltitel en -beschrijving in

Voeg een titel en beschrijving toe aan uw tabel:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Stap 10: Sta celafstand toe

Sta celafstand toe en stel de waarde ervan in voor een tabel:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Stap 11: Bouw een tafel met stijl

Maak een tabel met een vooraf gedefinieerde stijl:

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

## Stap 12: Vouw de opmaak van cellen en rijen uit vanuit stijl

Leer hoe u tabelstijlen uitbreidt om opmaak toe te passen op cellen en rijen:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Stap 13: Maak een tabelstijl

Maak een aangepaste tabelstijl met specifieke opmaak:

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

## Stap 14: Definieer voorwaardelijke opmaak

Voorwaardelijke opmaak toepassen op rijen in een tabel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Stap 15: Stel de TableCell-opmaak in

Stel specifieke opmaak in voor individuele cellen:

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

## Stap 16: Stel de TableRow-opmaak in

Pas opmaak toe op hele rijen in een tabel:

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

## Conclusie

Met Aspose.Words voor Java kunt u tabellen opmaken en tabelstijlen nauwkeurig toepassen. Van het wijzigen van de individuele celopmaak tot het maken van aangepaste tabelstijlen: u beschikt over de hulpmiddelen om uw documenten visueel aantrekkelijk en georganiseerd te maken.

## Veelgestelde vragen

### Hoe download ik Aspose.Words voor Java?

 U kunt Aspose.Words voor Java downloaden van de Aspose-website:[Download Aspose.Words voor Java](https://releases.aspose.com/words/java/).

### Kan ik verschillende randen toepassen op individuele cellen in een tabel?

Ja, u kunt verschillende randen instellen voor individuele cellen binnen een tabel met Aspose.Words voor Java, zoals gedemonstreerd in deze handleiding.

### Wat is het doel van het instellen van een tabeltitel en -beschrijving?

Het instellen van een tabeltitel en -beschrijving verbetert de toegankelijkheid en organisatie van uw document, waardoor het voor lezers en ondersteunende technologieën gemakkelijker wordt om de inhoud te begrijpen.

### Hoe kan ik voorwaardelijke opmaak toepassen op specifieke rijen in een tabel?

kunt voorwaardelijke opmaak toepassen op specifieke rijen in een tabel door aangepaste tabelstijlen te definiëren met regels voor voorwaardelijke opmaak, zoals weergegeven in deze handleiding.

### Waar kan ik meer documentatie en bronnen vinden voor Aspose.Words voor Java?

 Voor uitgebreide documentatie en aanvullende bronnen kunt u de Aspose.Words for Java-documentatie bezoeken:[Aspose.Words voor Java-documentatie](https://reference.aspose.com/words/java/).