---
title: Festlegen der Tabellenzeilenformatierung
linktitle: Festlegen der Tabellenzeilenformatierung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen der Tabellenzeilenformatierung mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen der Tabellenzeilenformatierung mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die Höhe und Auffüllung einer Tabellenzeile in Ihren Word-Dokumenten mit Aspose.Words für .NET anpassen.

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
Table table = builder. StartTable();
builder. InsertCell();
```

## Schritt 4: Zeilenformatierung festlegen
 Nun können wir die Zeilenformatierung festlegen, indem wir auf die`RowFormat` Gegenstand der`DocumentBuilder` Objekt. Die Zeilenhöhe und die Ränder (Paddings) können wir über die entsprechenden Eigenschaften festlegen.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Schritt 5: Tabellenränder festlegen
 Als nächstes können wir die Tabellenpolsterung festlegen, indem wir auf die entsprechenden Eigenschaften der`Table` Objekt. Diese Ränder werden auf alle Zeilen der Tabelle angewendet.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Schritt 6: Inhalt zur Zeile hinzufügen
 Schließlich können wir der Zeile mit dem Dokument-Builder Inhalt hinzufügen.`Writeln()` Methode.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Schritt 7: Tabelle fertigstellen und Dokument speichern
In

 Ende, wir beenden die Erstellung der Tabelle mit dem`EndRow()` Und`EndTable()` Methode, dann speichern wir das geänderte Dokument in einer Datei.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Beispielquellcode zum Festlegen der Tabellenzeilenformatierung mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Diese Formatierungseigenschaften werden für die Tabelle festgelegt und auf alle Zeilen in der Tabelle angewendet.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Tabellenzeilen mit Aspose.Words für .NET formatiert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Höhe und Ränder von Tabellenzeilen in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das visuelle Layout Ihrer Tabellen an Ihre spezifischen Anforderungen anpassen.