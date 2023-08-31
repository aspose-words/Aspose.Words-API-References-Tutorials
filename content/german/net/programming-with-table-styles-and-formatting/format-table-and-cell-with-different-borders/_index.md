---
title: Formatieren Sie Tabelle und Zelle mit unterschiedlichen Rändern
linktitle: Formatieren Sie Tabelle und Zelle mit unterschiedlichen Rändern
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Formatieren von Tabellen und Zellen mit unterschiedlichen Rändern mithilfe von Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Formatieren einer Tabelle und einer Zelle mit unterschiedlichen Rändern mithilfe von Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET benutzerdefinierte Rahmen auf bestimmte Tabellen und Zellen in Ihren Word-Dokumenten anwenden.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes Word-Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen Dokument-Builder
 Als nächstes müssen Sie eine neue Instanz von erstellen`Document` Klasse und einen Dokumentkonstruktor für dieses Dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Erstellen Sie eine neue Tabelle und fügen Sie Zellen hinzu
Um mit der Erstellung der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Document Builders, dann fügen wir der Tabelle Zellen hinzu, indem wir die verwenden`InsertCell()` Methode und wir schreiben den Inhalt der Zellen mit der`Writeln()` Methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Legen Sie Ränder für die gesamte Tabelle fest.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Legen Sie den Abstand für diese Zelle fest.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Geben Sie einen anderen Zellenabstand für die zweite Zelle an.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Zellenformatierung aus vorherigen Vorgängen löschen.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Erstellen Sie dickere Ränder für die erste Zelle in dieser Zeile. Es wird anders sein
// relativ zu den für die Tabelle definierten Rändern.
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
Speichern Sie abschließend das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument auswählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET eine Tabelle und eine Zelle mit unterschiedlichen Rändern formatiert.

### Beispielquellcode für das Formatieren von Tabellen und Zellen mit unterschiedlichen Rändern mithilfe von Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Legen Sie die Ränder für die gesamte Tabelle fest.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Legen Sie die Zellschattierung für diese Zelle fest.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Geben Sie für die zweite Zelle eine andere Zellschattierung an.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Löschen Sie die Zellenformatierung aus vorherigen Vorgängen.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Erstellen Sie größere Ränder für die erste Zelle dieser Zeile. Das wird anders sein
	// im Vergleich zu den für die Tabelle festgelegten Rändern.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle und eine Zelle mit unterschiedlichen Rändern formatiert. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie Ihre Tabellen- und Zellenränder in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.