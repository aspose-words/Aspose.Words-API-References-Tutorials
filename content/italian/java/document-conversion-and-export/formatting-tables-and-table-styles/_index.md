---
title: Formattazione di tabelle e stili di tabella in Aspose.Words per Java
linktitle: Formattazione di tabelle e stili di tabella
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come formattare le tabelle e applicare gli stili di tabella in Aspose.Words per Java. Esplora le guide dettagliate con il codice sorgente per una formattazione efficace delle tabelle. Migliora il layout del tuo documento con Aspose.Words.
type: docs
weight: 17
url: /it/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Introduzione alla formattazione di tabelle e stili di tabella in Aspose.Words per Java

Le tabelle svolgono un ruolo cruciale nella strutturazione e nell'organizzazione delle informazioni nei documenti. Aspose.Words per Java fornisce potenti funzionalità per la formattazione delle tabelle e l'applicazione di stili di tabella per migliorare l'attrattiva visiva dei tuoi documenti. In questa guida passo passo, esploreremo vari aspetti della formattazione delle tabelle e dell'applicazione degli stili di tabella utilizzando Aspose.Words per Java.

## Prerequisiti

Prima di immergerci nei dettagli, assicurati di avere la libreria Aspose.Words per Java integrata nel tuo progetto. Puoi scaricarlo dal sito Aspose:[Scarica Aspose.Words per Java](https://releases.aspose.com/words/java/).

## Ottieni la distanza tra la tabella e il testo circostante

Per iniziare, esploriamo come recuperare la distanza tra una tabella e il testo circostante in un documento.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Applica il bordo del contorno a una tabella

Puoi allineare una tabella al centro della pagina, cancellare i bordi esistenti e impostare un bordo personalizzato con questo codice:

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

## Costruisci una tabella con i bordi

Questo frammento di codice mostra come creare una tabella e impostare i bordi sia per la tabella che per le sue celle:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Modifica la formattazione della riga

Scopri come modificare la formattazione di una riga specifica all'interno di una tabella:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Applica formattazione riga

Questo esempio dimostra come applicare la formattazione a un'intera riga in una tabella:

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

## Imposta il riempimento delle celle

Scopri come impostare il riempimento per le singole celle in una tabella:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Modifica la formattazione della cella

Scopri come modificare la formattazione di una cella specifica all'interno di una tabella:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatta tabella e cella con bordi diversi

Scopri come impostare bordi diversi per le singole celle in una tabella:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Imposta i bordi della tabella
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Imposta l'ombreggiatura delle singole celle
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Aggiungi contenuto alle celle
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Cancella la formattazione della cella per la riga successiva
builder.getCellFormat().clearFormatting();
// Crea bordi più grandi per la prima cella di questa riga
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Imposta il titolo e la descrizione della tabella

Aggiungi un titolo e una descrizione alla tua tabella:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Passaggio 10: consentire la spaziatura delle celle

Consenti la spaziatura delle celle e imposta il suo valore per una tabella:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Passaggio 11: crea una tabella con stile

Crea una tabella con uno stile predefinito:

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

## Passaggio 12: espandere la formattazione su celle e righe da Stile

Scopri come espandere gli stili di tabella per applicare la formattazione a celle e righe:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Passaggio 13: crea uno stile di tabella

Crea uno stile di tabella personalizzato con formattazione specifica:

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

## Passaggio 14: definire la formattazione condizionale

Applicare la formattazione condizionale alle righe di una tabella:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Passaggio 15: impostare la formattazione di TableCell

Imposta la formattazione specifica per le singole celle:

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

## Passaggio 16: impostare la formattazione TableRow

Applica la formattazione a intere righe in una tabella:

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

## Conclusione

Aspose.Words per Java ti consente di formattare tabelle e applicare stili di tabella con precisione. Dalla modifica della formattazione delle singole celle alla creazione di stili di tabella personalizzati, hai gli strumenti per rendere i tuoi documenti visivamente accattivanti e organizzati.

## Domande frequenti

### Come posso scaricare Aspose.Words per Java?

 È possibile scaricare Aspose.Words per Java dal sito Web Aspose:[Scarica Aspose.Words per Java](https://releases.aspose.com/words/java/).

### Posso applicare bordi diversi alle singole celle all'interno di una tabella?

Sì, puoi impostare bordi diversi per singole celle all'interno di una tabella utilizzando Aspose.Words per Java, come dimostrato in questa guida.

### Qual è lo scopo di impostare il titolo e la descrizione di una tabella?

L'impostazione di un titolo e di una descrizione della tabella migliora l'accessibilità e l'organizzazione del documento, facilitando la comprensione del contenuto da parte dei lettori e delle tecnologie assistive.

### Come posso applicare la formattazione condizionale a righe specifiche in una tabella?

Puoi applicare la formattazione condizionale a righe specifiche in una tabella definendo stili di tabella personalizzati con regole di formattazione condizionale, come mostrato in questa guida.

### Dove posso trovare ulteriore documentazione e risorse per Aspose.Words per Java?

 Per documentazione completa e risorse aggiuntive, visitare la documentazione Aspose.Words per Java:[Aspose.Words per la documentazione Java](https://reference.aspose.com/words/java/).