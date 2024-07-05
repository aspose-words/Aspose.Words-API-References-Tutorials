---
title: Zellenpolster festlegen
linktitle: Zellenpolster festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen von Tabellenzellenrändern mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Tabellenzellenrändern mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie die linken, oberen, rechten und unteren Ränder (Abstand) des Zellinhalts in Ihren Tabellen in Ihren Word-Dokumenten mit Aspose.Words für .NET anpassen.

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

## Schritt 4: Zellränder festlegen
 Nun können wir die Zellränder mit dem`SetPaddings()` Methode der`CellFormat` Objekt. Ränder werden in Punkten definiert und in der Reihenfolge links, oben, rechts und unten angegeben.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
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
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Beispielquellcode für Set Cell Padding mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Legt den Abstand (in Punkten) fest, der links/oben/rechts/unten zum Zelleninhalt hinzugefügt werden soll.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Ränder einer Tabellenzelle mit Aspose.Words für .NET einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Zellränder ganz einfach anpassen, um links, oben, rechts und unten Platz für den Inhalt Ihrer Tabellen in Ihren Word-Dokumenten zu schaffen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die Formatierung Ihrer Tabellen an Ihre spezifischen Anforderungen anpassen.