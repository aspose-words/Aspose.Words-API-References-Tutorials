---
title: Zeilenformatierung anwenden
linktitle: Zeilenformatierung anwenden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Anwenden der Zeilenformatierung auf eine Tabelle mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Anwenden der Zeilenformatierung auf eine Tabelle mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials werden Sie ein klares Verständnis dafür haben, wie Sie Tabellenzeilen in Ihren Word-Dokumenten mit Aspose.Words für .NET formatieren.

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

## Schritt 3: Starten Sie ein neues Board
 Um die Zeilenformatierung anzuwenden, müssen wir zunächst eine neue Tabelle mit beginnen`StartTable()` Methode des Dokumentkonstruktors.

```csharp
Table table = builder. StartTable();
```

## Schritt 4: Zelle einfügen und zum Zeilenformat wechseln
Jetzt können wir eine Zelle in die Tabelle einfügen und mithilfe des Document Builders auf das Zeilenformat für diese Zelle zugreifen`InsertCell()` Und`RowFormat` Methoden.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Schritt 5: Zeilenhöhe festlegen
 Um die Zeilenhöhe festzulegen, verwenden wir die`Height` Und`HeightRule` Eigenschaften des Zeilenformats. In diesem Beispiel legen wir eine Zeilenhöhe von 100 Punkten fest und verwenden die`Exactly` Regel.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Schritt 6: Tabellenformatierung definieren
 Einige Formatierungseigenschaften können in der Tabelle selbst festgelegt werden und werden auf alle Tabellenzeilen angewendet. In diesem Beispiel legen wir die Tabellenrandeigenschaften mithilfe von fest`LeftPadding`, `RightPadding`, `TopPadding` Und`BottomPadding` Eigenschaften.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Schritt 7: Fügen Sie der Zeile Inhalte hinzu
Jetzt können wir

 Wir werden der Zeile mithilfe der Methoden des Dokumentkonstruktors Inhalte hinzufügen. In diesem Beispiel verwenden wir die`Writeln()` Methode zum Hinzufügen von Text zur Zeile.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Schritt 8: Beenden Sie die Linie und den Tisch
 Sobald wir den Inhalt zur Zeile hinzugefügt haben, können wir die Zeile mit beenden`EndRow()` Methode und beenden Sie dann die Tabelle mit der`EndTable()` Methode.

```csharp
builder. EndRow();
builder. EndTable();
```

## Schritt 9: Speichern Sie das geänderte Dokument
Abschließend speichern wir das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument auswählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Herzlichen Glückwunsch! Sie haben nun mit Aspose.Words für .NET die Zeilenformatierung auf eine Tabelle angewendet.

### Beispielquellcode für „Zeilenformatierung anwenden“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Zeilenformatierung auf eine Tabelle anwendet. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktionalität problemlos in Ihre C#-Projekte integrieren. Die Manipulation der Formatierung von Tabellenzeilen ist ein wesentlicher Aspekt der Dokumentverarbeitung, und Aspose.Words bietet eine leistungsstarke und flexible API, um dies zu erreichen. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.