---
title: Festlegen der Tabellenzellenformatierung
linktitle: Festlegen der Tabellenzellenformatierung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen der Tabellenzellenformatierung mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Definieren der Formatierung einer Tabellenzelle mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die Breite und die Ränder (Abstände) einer Zelle in Ihren Tabellen Ihrer Word-Dokumente mit Aspose.Words für .NET anpassen.

## Schritt 1: Dokumentverzeichnis festlegen
Zunächst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes Word-Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Neues Dokument und Dokumentgenerator erstellen
 Als nächstes müssen Sie eine neue Instanz des`Document` Klasse und ein Dokumentkonstruktor für dieses Dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Neue Tabelle erstellen und Zelle hinzufügen
Um mit der Erstellung der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Dokumentkonstruktors, dann fügen wir der Tabelle eine Zelle hinzu mit der`InsertCell()` Methode.

```csharp
builder. StartTable();
builder. InsertCell();
```

## Schritt 4: Zellenformatierung festlegen
 Nun können wir die Zellenformatierung festlegen, indem wir auf die`CellFormat` Gegenstand der`DocumentBuilder` Objekt. Wir können die Zellenbreite und die Ränder (Paddings) mit den entsprechenden Eigenschaften festlegen.

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## Schritt 5: Inhalt zur Zelle hinzufügen
 Anschließend können wir der Zelle Inhalt hinzufügen, indem wir den Dokumentgenerator verwenden.`Writeln()` Methode.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Schritt 6: Tabelle fertigstellen und Dokument speichern
 Zum Schluss erstellen wir die Tabelle mit dem`EndRow()` Methode und`EndTable()`, dann speichern wir das geänderte Dokument in einer Datei.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### Beispielquellcode zum Festlegen der Tabellenzellenformatierung mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Formatierung einer Tabellenzelle mit Aspose.Words für .NET einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Breite und Ränder einer Zelle in Ihren Tabellen in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das visuelle Layout Ihrer Tabellen an Ihre spezifischen Bedürfnisse anpassen.