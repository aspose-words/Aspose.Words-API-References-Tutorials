---
title: Formatieren von Tabellen und Tabellenstilen in Aspose.Words für Java
linktitle: Formatieren von Tabellen und Tabellenstilen
second_title: Aspose.Words Java-API zur Dokumentverarbeitung
description: Erfahren Sie, wie Sie Tabellen formatieren und Tabellenstile in Aspose.Words für Java anwenden. Entdecken Sie Schritt-für-Schritt-Anleitungen mit Quellcode für eine effektive Tabellenformatierung. Verbessern Sie Ihr Dokumentlayout mit Aspose.Words.
type: docs
weight: 17
url: /de/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Einführung in die Formatierung von Tabellen und Tabellenstilen in Aspose.Words für Java

Tabellen spielen eine entscheidende Rolle bei der Strukturierung und Organisation von Informationen in Dokumenten. Aspose.Words für Java bietet leistungsstarke Funktionen zum Formatieren von Tabellen und Anwenden von Tabellenstilen, um die visuelle Attraktivität Ihrer Dokumente zu verbessern. In dieser Schritt-für-Schritt-Anleitung untersuchen wir verschiedene Aspekte des Formatierens von Tabellen und Anwendens von Tabellenstilen mit Aspose.Words für Java.

## Voraussetzungen

Bevor wir in die Details eintauchen, stellen Sie sicher, dass Sie die Aspose.Words für Java-Bibliothek in Ihr Projekt integriert haben. Sie können sie von der Aspose-Website herunterladen:[Laden Sie Aspose.Words für Java herunter](https://releases.aspose.com/words/java/).

## Abstand zwischen Tabelle und umgebendem Text ermitteln

Sehen wir uns zunächst an, wie Sie den Abstand zwischen einer Tabelle und dem umgebenden Text in einem Dokument abrufen können.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Anwenden einer Gliederungsgrenze auf eine Tabelle

Mit diesem Code können Sie eine Tabelle in der Seitenmitte ausrichten, vorhandene Rahmen löschen und einen benutzerdefinierten Gliederungsrahmen festlegen:

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

## Erstellen Sie eine Tabelle mit Rahmen

Dieser Codeausschnitt zeigt, wie Sie eine Tabelle erstellen und Rahmen für die Tabelle und ihre Zellen festlegen:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Zeilenformatierung ändern

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

Dieses Beispiel zeigt, wie Sie die Formatierung auf eine ganze Zeile einer Tabelle anwenden:

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

## Zellenpolster festlegen

Erfahren Sie, wie Sie die Innenabstände für einzelne Zellen in einer Tabelle festlegen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Zellenformatierung ändern

Erfahren Sie, wie Sie die Formatierung einer bestimmten Zelle in einer Tabelle ändern:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Tabelle und Zelle mit unterschiedlichen Rändern formatieren

Erfahren Sie, wie Sie für einzelne Zellen in einer Tabelle unterschiedliche Rahmen festlegen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Festlegen der Tabellenränder
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Festlegen der Zellenschattierung für einzelne Zellen
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Hinzufügen von Inhalten zu den Zellen
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Zellenformatierung für die nächste Zeile löschen
builder.getCellFormat().clearFormatting();
// Größere Ränder für die erste Zelle dieser Zeile erstellen
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Tabellentitel und -beschreibung festlegen

Fügen Sie Ihrer Tabelle einen Titel und eine Beschreibung hinzu:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Schritt 10: Zellenabstand zulassen

Lassen Sie den Zellenabstand zu und legen Sie seinen Wert für eine Tabelle fest:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Schritt 11: Bauen Sie einen Tisch mit Stil

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

## Schritt 12: Erweitern Sie die Formatierung auf Zellen und Zeilen aus dem Stil

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

Erstellen Sie einen benutzerdefinierten Tabellenstil mit bestimmter Formatierung:

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

Wenden Sie eine bedingte Formatierung auf Zeilen in einer Tabelle an:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Schritt 15: Tabellenzellenformatierung festlegen

Legen Sie für einzelne Zellen spezifische Formatierungen fest:

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

## Schritt 16: Tabellenzeilenformatierung festlegen

Formatierung auf ganze Zeilen in einer Tabelle anwenden:

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

Mit Aspose.Words für Java können Sie Tabellen formatieren und Tabellenstile präzise anwenden. Von der Änderung der Formatierung einzelner Zellen bis hin zur Erstellung benutzerdefinierter Tabellenstile verfügen Sie über die Tools, um Ihre Dokumente optisch ansprechend und übersichtlich zu gestalten.

## Häufig gestellte Fragen

### Wie lade ich Aspose.Words für Java herunter?

 Sie können Aspose.Words für Java von der Aspose-Website herunterladen:[Laden Sie Aspose.Words für Java herunter](https://releases.aspose.com/words/java/).

### Kann ich einzelnen Zellen einer Tabelle unterschiedliche Rahmen zuweisen?

Ja, Sie können mit Aspose.Words für Java unterschiedliche Ränder für einzelne Zellen in einer Tabelle festlegen, wie in diesem Handbuch gezeigt.

### Welchen Zweck hat das Festlegen eines Tabellentitels und einer Tabellenbeschreibung?

Durch das Festlegen eines Tabellentitels und einer Tabellenbeschreibung verbessern Sie die Zugänglichkeit und Organisation Ihres Dokuments und erleichtern Lesern und unterstützenden Technologien das Verständnis des Inhalts.

### Wie kann ich eine bedingte Formatierung auf bestimmte Zeilen in einer Tabelle anwenden?

Sie können bedingte Formatierung auf bestimmte Zeilen in einer Tabelle anwenden, indem Sie benutzerdefinierte Tabellenstile mit Regeln zur bedingten Formatierung definieren, wie in diesem Handbuch gezeigt.

### Wo finde ich weitere Dokumentation und Ressourcen für Aspose.Words für Java?

 Umfassende Dokumentation und zusätzliche Ressourcen finden Sie in der Dokumentation zu Aspose.Words für Java:[Aspose.Words für Java-Dokumentation](https://reference.aspose.com/words/java/).