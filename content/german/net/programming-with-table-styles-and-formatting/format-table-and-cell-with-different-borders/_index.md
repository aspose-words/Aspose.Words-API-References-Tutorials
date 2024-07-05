---
title: Tabelle und Zelle mit unterschiedlichen Rändern formatieren
linktitle: Tabelle und Zelle mit unterschiedlichen Rändern formatieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Formatieren von Tabellen und Zellen mit unterschiedlichen Rändern mithilfe von Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Formatieren einer Tabelle und einer Zelle mit unterschiedlichen Rändern mithilfe von Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mit Aspose.Words für .NET benutzerdefinierte Ränder auf bestimmte Tabellen und Zellen in Ihren Word-Dokumenten anwenden.

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

## Schritt 3: Neue Tabelle erstellen und Zellen hinzufügen
Um mit der Erstellung der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Dokument-Generators, dann fügen wir Zellen zur Tabelle hinzu mit der`InsertCell()` Methode und wir schreiben den Inhalt der Zellen in die mit der`Writeln()` Methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Legen Sie die Grenzen für die gesamte Tabelle fest.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Legen Sie die Polsterung für diese Zelle fest.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Geben Sie für die zweite Zelle eine andere Zellenauffüllung an.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Löschen Sie die Zellenformatierung aus vorherigen Vorgängen.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Erstellen Sie dickere Ränder für die erste Zelle in dieser Zeile. Sie wird anders sein
// relativ zu den für die Tabelle definierten Grenzen.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Schritt 4: Speichern Sie das Dokument

  geändert
Speichern Sie das geänderte Dokument abschließend in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument wählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET eine Tabelle und eine Zelle mit unterschiedlichen Rändern formatiert.

### Beispiel-Quellcode zum Formatieren von Tabellen und Zellen mit unterschiedlichen Rändern unter Verwendung von Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Legen Sie die Grenzen für die gesamte Tabelle fest.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Legen Sie die Zellenschattierung für diese Zelle fest.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Geben Sie für die zweite Zelle eine andere Zellenschattierung an.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Löschen Sie die Zellenformatierung aus vorherigen Vorgängen.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Erstellen Sie größere Ränder für die erste Zelle dieser Zeile. Das wird anders sein
	// im Vergleich zu den für die Tabelle festgelegten Grenzen.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle und eine Zelle mit unterschiedlichen Rändern formatiert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie Ihre Tabellen- und Zellenränder in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.