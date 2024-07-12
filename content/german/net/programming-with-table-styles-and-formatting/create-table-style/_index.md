---
title: Tabellenstil erstellen
linktitle: Tabellenstil erstellen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erstellen eines benutzerdefinierten Tabellenstils mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/create-table-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Erstellen eines Tabellenstils mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mit Aspose.Words für .NET einen benutzerdefinierten Stil für Ihre Tabellen in Ihren Word-Dokumenten erstellen.

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
Um mit der Erstellung der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Dokument-Generators, dann fügen wir Zellen zur Tabelle hinzu mit der`InsertCell()` Methode und wir schreiben den Inhalt der Zellen in die mit der`Write()` Methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Schritt 4: Einen Tabellenstil erstellen
 Nun können wir einen Tabellenstil erstellen mit dem`TableStyle` Klasse und die`Add()` Methode aus dem Dokument`s `Stilsammlung. Wir definieren die Eigenschaften des Stils, wie Ränder, Abstände und Polsterungen.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Schritt 5: Tabellenstil auf die Tabelle anwenden
 Zum Schluss wenden wir den erstellten Tabellenstil auf die Tabelle an, indem wir`Style` Eigenschaft der Tabelle.

```csharp
table.Style = tableStyle;
```

## Schritt 6: Speichern Sie das geänderte Dokument
Speichern Sie das geänderte Dokument abschließend in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument wählen.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET einen benutzerdefinierten Stil für Ihre Tabelle erstellt.

### Beispielquellcode zum Erstellen eines Tabellenstils mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET einen Tabellenstil erstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie den Stil Ihrer Tabellen in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.