---
title: Bauen Sie einen Tisch mit Stil
linktitle: Bauen Sie einen Tisch mit Stil
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erstellen einer Tabelle mit einem benutzerdefinierten Stil mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Erstellen einer formatierten Tabelle mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mit Aspose.Words für .NET eine Tabelle mit einem benutzerdefinierten Format in Ihren Word-Dokumenten erstellen.

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

## Schritt 3: Neue Tabelle starten und Zelle einfügen
 Um mit dem Erstellen der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Dokument-Builders, dann fügen wir eine Zelle in die Tabelle ein mit der`InsertCell()` Methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Schritt 4: Definieren Sie den Stil der Tabelle
 Nun können wir den Tabellenstil mit dem`StyleIdentifier` Eigenschaft. In diesem Beispiel verwenden wir den Stil „MediumShading1Accent1“.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Schritt 5: Stiloptionen auf die Tabelle anwenden
 Wir können angeben, welche Merkmale durch den Stil formatiert werden sollen, indem wir`StyleOptions`Eigenschaft des Arrays. In diesem Beispiel wenden wir die folgenden Optionen an: „FirstColumn“, „RowBands“ und „FirstRow“.

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Schritt 6: Tabellengröße automatisch anpassen
 Um die Größe des Arrays automatisch an seinen Inhalt anzupassen, verwenden wir die`AutoFit()` Methode mit dem`AutoFitBehavior.AutoFitToContents` Verhalten.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Schritt 7: Inhalt zu Zellen hinzufügen
 Nun können wir Inhalt zu Zellen hinzufügen, indem wir`Writeln()` Und`InsertCell()` Methoden des Dokumentgenerators. In diesem Beispiel fügen wir die Überschriften für "Artikel" und "Menge" hinzu (

kg)“ und die dazugehörigen Daten.

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
Abschließend speichern wir das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument wählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET eine benutzerdefiniert gestaltete Tabelle erstellt.

### Beispielquellcode für „Build Table With Style“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Wir müssen zuerst mindestens eine Zeile einfügen, bevor wir eine Tabellenformatierung festlegen.
	builder.InsertCell();
	// Legen Sie den verwendeten Tabellenstil basierend auf der eindeutigen Stilkennung fest.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Geben Sie an, welche Features durch den Stil formatiert werden sollen.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine formatierte Tabelle erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie den Stil Ihrer Tabellen in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.