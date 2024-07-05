---
title: Zeilenformatierung anwenden
linktitle: Zeilenformatierung anwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Anwenden der Zeilenformatierung auf eine Tabelle mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, mit Aspose.Words für .NET Zeilenformatierung auf eine Tabelle anzuwenden. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials haben Sie ein klares Verständnis dafür, wie Sie Tabellenzeilen in Ihren Word-Dokumenten mit Aspose.Words für .NET formatieren.

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

## Schritt 3: Ein neues Board starten
 Um die Zeilenformatierung anzuwenden, müssen wir zunächst eine neue Tabelle mit dem`StartTable()` Methode des Dokumentkonstruktors.

```csharp
Table table = builder. StartTable();
```

## Schritt 4: Zelle einfügen und zum Zeilenformat wechseln
Jetzt können wir eine Zelle in die Tabelle einfügen und das Zeilenformat für diese Zelle mit dem Dokument-Generator aufrufen.`InsertCell()` Und`RowFormat` Methoden.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Schritt 5: Zeilenhöhe festlegen
 Um die Zeilenhöhe einzustellen, verwenden wir die`Height` Und`HeightRule` Eigenschaften des Zeilenformats. In diesem Beispiel setzen wir eine Zeilenhöhe von 100 Punkten und verwenden die`Exactly` Regel.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Schritt 6: Tabellenformatierung festlegen
 Einige Formatierungseigenschaften können in der Tabelle selbst festgelegt werden und werden auf alle Tabellenzeilen angewendet. In diesem Beispiel legen wir die Tabellenrandeigenschaften mithilfe der`LeftPadding`, `RightPadding`, `TopPadding` Und`BottomPadding` Eigenschaften.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Schritt 7: Inhalt zur Zeile hinzufügen
Jetzt können wir

 Wir werden der Zeile Inhalt hinzufügen, indem wir die Methoden des Dokumentkonstruktors verwenden. In diesem Beispiel verwenden wir die`Writeln()` Methode zum Hinzufügen von Text zur Zeile.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Schritt 8: Linie und Tabelle fertigstellen
 Sobald wir den Inhalt zur Zeile hinzugefügt haben, können wir die Zeile beenden mit dem`EndRow()` -Methode und beenden Sie die Tabelle anschließend mit der`EndTable()` Methode.

```csharp
builder. EndRow();
builder. EndTable();
```

## Schritt 9: Speichern Sie das geänderte Dokument
Abschließend speichern wir das geänderte Dokument in einer Datei. Sie können einen geeigneten Namen und Speicherort für das Ausgabedokument wählen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Herzlichen Glückwunsch! Sie haben jetzt mit Aspose.Words für .NET eine Zeilenformatierung auf eine Tabelle angewendet.

### Beispielquellcode zum Anwenden der Zeilenformatierung mit Aspose.Words für .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Zeilenformatierungen auf eine Tabelle anwendet. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktionalität problemlos in Ihre C#-Projekte integrieren. Die Manipulation der Tabellenzeilenformatierung ist ein wesentlicher Aspekt der Dokumentverarbeitung, und Aspose.Words bietet hierfür eine leistungsstarke und flexible API. Mit diesem Wissen können Sie die visuelle Darstellung Ihrer Word-Dokumente verbessern und spezifische Anforderungen erfüllen.