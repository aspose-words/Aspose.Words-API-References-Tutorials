---
title: Formatieren von Tabellen und Tabellenstilen in Aspose.Words für Java
linktitle: Formatieren von Tabellen und Tabellenstilen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Tabellen formatieren und Tabellenstile in Aspose.Words für Java anwenden. Entdecken Sie Schritt-für-Schritt-Anleitungen mit Quellcode für eine effektive Tabellenformatierung. Verbessern Sie Ihr Dokumentlayout mit Aspose.Words.
type: docs
weight: 17
url: /de/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Einführung in die Formatierung von Tabellen und Tabellenstilen in Aspose.Words für Java

Tabellen spielen eine entscheidende Rolle bei der Strukturierung und Organisation von Informationen in Dokumenten. Aspose.Words für Java bietet leistungsstarke Funktionen zum Formatieren von Tabellen und Anwenden von Tabellenstilen, um die visuelle Attraktivität Ihrer Dokumente zu verbessern. In dieser Schritt-für-Schritt-Anleitung untersuchen wir verschiedene Aspekte der Formatierung von Tabellen und der Anwendung von Tabellenstilen mit Aspose.Words für Java.

## Voraussetzungen

Bevor wir uns mit den Details befassen, stellen Sie sicher, dass Sie die Aspose.Words for Java-Bibliothek in Ihr Projekt integriert haben. Sie können es von der Aspose-Website herunterladen:[Laden Sie Aspose.Words für Java herunter](https://releases.aspose.com/words/java/).

## Ermitteln Sie den Abstand zwischen der Tabelle und dem umgebenden Text

Lassen Sie uns zunächst untersuchen, wie Sie den Abstand zwischen einer Tabelle und dem umgebenden Text in einem Dokument ermitteln.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Wenden Sie einen Umrissrahmen auf eine Tabelle an

Mit diesem Code können Sie eine Tabelle an der Mitte der Seite ausrichten, vorhandene Ränder löschen und einen benutzerdefinierten Umrissrahmen festlegen:

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

## Erstellen Sie eine Tabelle mit Rändern

Dieser Codeausschnitt zeigt, wie Sie eine Tabelle erstellen und Rahmen für die Tabelle und ihre Zellen festlegen:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Ändern Sie die Zeilenformatierung

Erfahren Sie, wie Sie die Formatierung einer bestimmten Zeile in einer Tabelle ändern:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Zeilenformatierung anwenden

Dieses Beispiel zeigt, wie Formatierung auf eine ganze Zeile in einer Tabelle angewendet wird:

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

## Zellauffüllung festlegen

Erfahren Sie, wie Sie den Abstand für einzelne Zellen in einer Tabelle festlegen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Ändern Sie die Zellformatierung

Erfahren Sie, wie Sie die Formatierung einer bestimmten Zelle in einer Tabelle ändern:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatieren Sie Tabelle und Zelle mit unterschiedlichen Rändern

Erfahren Sie, wie Sie unterschiedliche Ränder für einzelne Zellen in einer Tabelle festlegen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Legen Sie die Tischränder fest
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Legen Sie die Zellschattierung für einzelne Zellen fest
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Fügen Sie Inhalt zu den Zellen hinzu
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Zellenformatierung für die nächste Zeile löschen
builder.getCellFormat().clearFormatting();
// Erstellen Sie größere Ränder für die erste Zelle dieser Zeile
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Legen Sie den Tabellentitel und die Beschreibung fest

Fügen Sie Ihrer Tabelle einen Titel und eine Beschreibung hinzu:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Schritt 10: Zellabstand zulassen

Erlauben Sie den Zellenabstand und legen Sie seinen Wert für eine Tabelle fest:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Schritt 11: Erstellen Sie einen Tisch mit Stil

Erstellen Sie eine Tabelle mit einem vordefinierten Stil:

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

## Schritt 12: Erweitern Sie die Formatierung für Zellen und Zeilen unter „Stil“.

Erfahren Sie, wie Sie Tabellenstile erweitern, um Formatierungen auf Zellen und Zeilen anzuwenden:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Schritt 13: Erstellen Sie einen Tabellenstil

Erstellen Sie einen benutzerdefinierten Tabellenstil mit spezifischer Formatierung:

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

## Schritt 14: Bedingte Formatierung definieren

Wenden Sie bedingte Formatierung auf Zeilen in einer Tabelle an:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Schritt 15: Legen Sie die TableCell-Formatierung fest

Legen Sie spezifische Formatierungen für einzelne Zellen fest:

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

## Schritt 16: TableRow-Formatierung festlegen

Wenden Sie die Formatierung auf ganze Zeilen in einer Tabelle an:

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

## Abschluss

Mit Aspose.Words für Java können Sie Tabellen präzise formatieren und Tabellenstile anwenden. Von der Änderung der Formatierung einzelner Zellen bis hin zur Erstellung benutzerdefinierter Tabellenstile verfügen Sie über die Tools, mit denen Sie Ihre Dokumente optisch ansprechend und organisiert gestalten können.

## FAQs

### Wie lade ich Aspose.Words für Java herunter?

 Sie können Aspose.Words für Java von der Aspose-Website herunterladen:[Laden Sie Aspose.Words für Java herunter](https://releases.aspose.com/words/java/).

### Kann ich einzelne Zellen innerhalb einer Tabelle unterschiedlich umranden?

Ja, Sie können mit Aspose.Words für Java unterschiedliche Rahmen für einzelne Zellen innerhalb einer Tabelle festlegen, wie in diesem Handbuch gezeigt.

### Was ist der Zweck, einen Tabellentitel und eine Beschreibung festzulegen?

Das Festlegen eines Tabellentitels und einer Tabellenbeschreibung verbessert die Zugänglichkeit und Organisation Ihres Dokuments und erleichtert Lesern und unterstützenden Technologien das Verständnis des Inhalts.

### Wie kann ich bedingte Formatierung auf bestimmte Zeilen in einer Tabelle anwenden?

Sie können bedingte Formatierung auf bestimmte Zeilen in einer Tabelle anwenden, indem Sie benutzerdefinierte Tabellenstile mit Regeln für bedingte Formatierung definieren, wie in diesem Handbuch gezeigt.

### Wo finde ich weitere Dokumentation und Ressourcen für Aspose.Words für Java?

 Eine umfassende Dokumentation und zusätzliche Ressourcen finden Sie in der Dokumentation zu Aspose.Words für Java:[Aspose.Words für Java-Dokumentation](https://reference.aspose.com/words/java/).