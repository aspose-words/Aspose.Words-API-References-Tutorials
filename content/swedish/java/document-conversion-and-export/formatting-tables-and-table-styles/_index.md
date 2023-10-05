---
title: Formatera tabeller och tabellstilar i Aspose.Words för Java
linktitle: Formatera tabeller och tabellstilar
second_title: Aspose.Words Java Document Processing API
description: Lär dig hur du formaterar tabeller och tillämpar tabellstilar i Aspose.Words för Java. Utforska steg-för-steg-guider med källkod för effektiv tabellformatering. Förbättra din dokumentlayout med Aspose.Words.
type: docs
weight: 17
url: /sv/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Introduktion till formatering av tabeller och tabellstilar i Aspose.Words för Java

Tabeller spelar en avgörande roll för att strukturera och organisera information i dokument. Aspose.Words för Java tillhandahåller kraftfulla funktioner för att formatera tabeller och tillämpa tabellstilar för att förbättra det visuella tilltalande av dina dokument. I den här steg-för-steg-guiden kommer vi att utforska olika aspekter av att formatera tabeller och tillämpa tabellstilar med Aspose.Words för Java.

## Förutsättningar

Innan vi dyker in i detaljerna, se till att du har Aspose.Words for Java-biblioteket integrerat i ditt projekt. Du kan ladda ner den från Asposes webbplats:[Ladda ner Aspose.Words för Java](https://releases.aspose.com/words/java/).

## Få avstånd mellan tabell och omgivande text

Låt oss börja med att utforska hur man hämtar avståndet mellan en tabell och den omgivande texten i ett dokument.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Applicera konturkant på en tabell

Du kan anpassa en tabell till mitten av sidan, rensa befintliga ramar och ställa in en anpassad konturkant med denna kod:

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

## Bygg ett bord med gränser

Det här kodavsnittet visar hur man skapar en tabell och ställer in gränser för både tabellen och dess celler:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Ändra radformatering

Lär dig hur du ändrar formateringen av en specifik rad i en tabell:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Använd radformatering

Det här exemplet visar hur man tillämpar formatering på en hel rad i en tabell:

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

## Ställ in cellutfyllnad

Utforska hur du ställer in utfyllnad för enskilda celler i en tabell:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Ändra cellformatering

Upptäck hur du ändrar formateringen av en specifik cell i en tabell:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatera tabell och cell med olika ramar

Lär dig hur du ställer in olika ramar för enskilda celler i en tabell:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Ställ in bordskanterna
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Ställ in cellskuggning för enskilda celler
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Lägg till innehåll i cellerna
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Rensa cellformatering för nästa rad
builder.getCellFormat().clearFormatting();
// Skapa större ramar för den första cellen i denna rad
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Ställ in tabelltitel och beskrivning

Lägg till en titel och beskrivning till din tabell:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Steg 10: Tillåt cellavstånd

Tillåt cellavstånd och ställ in dess värde för en tabell:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Steg 11: Bygg ett bord med stil

Skapa en tabell med en fördefinierad stil:

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

## Steg 12: Expandera formatering på celler och rader från stil

Lär dig hur du utökar tabellstilar för att tillämpa formatering på celler och rader:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Steg 13: Skapa en tabellstil

Skapa en anpassad tabellstil med specifik formatering:

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

## Steg 14: Definiera villkorlig formatering

Tillämpa villkorlig formatering på rader i en tabell:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Steg 15: Ställ in tabellcellsformatering

Ställ in specifik formatering för enskilda celler:

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

## Steg 16: Ställ in TableRow-formatering

Tillämpa formatering på hela rader i en tabell:

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

## Slutsats

Aspose.Words för Java ger dig möjlighet att formatera tabeller och tillämpa tabellstilar med precision. Från att ändra individuell cellformatering till att skapa anpassade tabellstilar, du har verktygen för att göra dina dokument visuellt tilltalande och organiserade.

## FAQ's

### Hur laddar jag ner Aspose.Words för Java?

 Du kan ladda ner Aspose.Words för Java från Asposes webbplats:[Ladda ner Aspose.Words för Java](https://releases.aspose.com/words/java/).

### Kan jag använda olika ramar på enskilda celler i en tabell?

Ja, du kan ställa in olika ramar för enskilda celler i en tabell med Aspose.Words för Java, som visas i den här guiden.

### Vad är syftet med att ange en tabelltitel och beskrivning?

Att sätta en tabelltitel och beskrivning förbättrar tillgängligheten och organisationen av ditt dokument, vilket gör det lättare för läsare och hjälpmedel att förstå innehållet.

### Hur kan jag tillämpa villkorlig formatering på specifika rader i en tabell?

Du kan tillämpa villkorlig formatering på specifika rader i en tabell genom att definiera anpassade tabellstilar med regler för villkorlig formatering, som visas i den här guiden.

### Var kan jag hitta mer dokumentation och resurser för Aspose.Words för Java?

 För omfattande dokumentation och ytterligare resurser, besök Aspose.Words for Java-dokumentationen:[Aspose.Words för Java-dokumentation](https://reference.aspose.com/words/java/).