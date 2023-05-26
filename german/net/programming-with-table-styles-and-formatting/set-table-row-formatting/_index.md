---
title: Legen Sie die Formatierung der Tabellenzeile fest
linktitle: Legen Sie die Formatierung der Tabellenzeile fest
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen der Tabellenzeilenformatierung mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen der Tabellenzeilenformatierung mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET die Höhe und den Abstand einer Tabellenzeile in Ihren Word-Dokumenten anpassen.

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

## Schritt 3: Erstellen Sie eine neue Tabelle und fügen Sie eine Zelle hinzu
Um mit der Erstellung der Tabelle zu beginnen, verwenden wir die`StartTable()` Methode des Dokumentkonstruktors, dann fügen wir der Tabelle eine Zelle hinzu, indem wir die verwenden`InsertCell()` Methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Schritt 4: Definieren Sie die Zeilenformatierung
 Jetzt können wir die Zeilenformatierung festlegen, indem wir auf zugreifen`RowFormat` Gegenstand der`DocumentBuilder` Objekt. Die Zeilenhöhe und die Ränder (Abstände) können wir über die entsprechenden Eigenschaften festlegen.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Schritt 5: Tabellenränder festlegen
 Als nächstes können wir die Tabellenabstände festlegen, indem wir auf die entsprechenden Eigenschaften der zugreifen`Table` Objekt. Diese Ränder werden auf alle Zeilen der Tabelle angewendet.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Schritt 6: Fügen Sie der Zeile Inhalte hinzu
 Schließlich können wir mit dem Document Builder Inhalte zur Zeile hinzufügen`Writeln()` Methode.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Schritt 7: Beenden Sie die Tabelle und speichern Sie das Dokument
In

 Am Ende schließen wir die Erstellung der Tabelle mit dem ab`EndRow()` Und`EndTable()` Dann speichern wir das geänderte Dokument in einer Datei.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Beispielquellcode zum Festlegen der Tabellenzeilenformatierung mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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
In diesem Tutorial haben wir gelernt, wie man die Tabellenzeilenformatierung mit Aspose.Words für .NET festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Tabellenzeilenhöhe und -ränder in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das visuelle Layout Ihrer Tabellen an Ihre spezifischen Bedürfnisse anpassen.