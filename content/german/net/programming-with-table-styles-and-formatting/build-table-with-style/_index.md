---
title: Bauen Sie einen Tisch mit Stil
linktitle: Bauen Sie einen Tisch mit Stil
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erstellen einer Tabelle mit einem benutzerdefinierten Stil mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Erstellen einer gestalteten Tabelle mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle mit einem benutzerdefinierten Stil in Ihren Word-Dokumenten erstellen.

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

## Schritt 3: Erstellen Sie eine neue Tabelle und fügen Sie eine Zelle ein
 Um mit dem Aufbau der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Document Builders, dann fügen wir mit der eine Zelle in die Tabelle ein`InsertCell()` Methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Schritt 4: Definieren Sie den Stil der Tabelle
 Jetzt können wir den Tabellenstil mit festlegen`StyleIdentifier` Eigentum. In diesem Beispiel verwenden wir den Stil „MediumShading1Accent1“.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Schritt 5: Wenden Sie Stiloptionen auf die Tabelle an
 Mit können wir festlegen, welche Merkmale durch den Stil formatiert werden sollen`StyleOptions`Eigenschaft des Arrays. In diesem Beispiel wenden wir die folgenden Optionen an: „FirstColumn“, „RowBands“ und „FirstRow“.

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Schritt 6: Tabellengröße automatisch anpassen
 Um die Größe des Arrays basierend auf seinem Inhalt automatisch anzupassen, verwenden wir die`AutoFit()` Methode mit der`AutoFitBehavior.AutoFitToContents` Verhalten.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Schritt 7: Inhalte zu Zellen hinzufügen
 Jetzt können wir mit dem Inhalt zu Zellen hinzufügen`Writeln()` Und`InsertCell()` Methoden des Document Builders. In diesem Beispiel fügen wir die Überschriften für „Artikel“ und „Menge“ hinzu (

kg)“ und die entsprechenden Daten.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Schritt 8: Speichern Sie das geänderte Dokument
Abschließend speichern wir das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument auswählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET eine benutzerdefinierte gestaltete Tabelle erstellt.

### Beispielquellcode für Build Table With Style mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Wir müssen zuerst mindestens eine Zeile einfügen, bevor wir eine Tabellenformatierung festlegen.
	builder.InsertCell();
	// Legen Sie den verwendeten Tabellenstil basierend auf der eindeutigen Stilkennung fest.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Anwenden, welche Features durch den Stil formatiert werden sollen.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine gestaltete Tabelle erstellt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie den Stil Ihrer Tabellen in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.