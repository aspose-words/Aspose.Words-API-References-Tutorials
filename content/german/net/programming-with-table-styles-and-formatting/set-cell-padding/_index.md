---
title: Zellauffüllung festlegen
linktitle: Zellauffüllung festlegen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen von Tabellenzellenrändern mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen von Tabellenzellenrändern mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET den linken, oberen, rechten und unteren Rand (Abstand) des Zellinhalts in Ihren Tabellen in Ihren Word-Dokumenten anpassen.

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
builder. StartTable();
builder. InsertCell();
```

## Schritt 4: Zellränder festlegen
 Jetzt können wir die Zellränder mit festlegen`SetPaddings()` Methode der`CellFormat` Objekt. Ränder werden in Punkten definiert und in der Reihenfolge links, oben, rechts und unten angegeben.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Schritt 5: Inhalt zur Zelle hinzufügen
 Anschließend können wir mit dem Document Builder Inhalte zur Zelle hinzufügen`Writeln()` Methode.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Schritt 6: Beenden Sie die Tabelle und speichern Sie das Dokument
 Schließlich beenden wir die Erstellung der Tabelle mithilfe von`EndRow()` Methode und`EndTable()`, dann speichern wir das geänderte Dokument in einer Datei.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Beispielquellcode für „Set Cell Padding“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Legt die Menge an Platz (in Punkten) fest, die links/oben/rechts/unten zum Inhalt der Zelle hinzugefügt werden soll.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Ränder einer Tabellenzelle festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Zellränder ganz einfach anpassen, um in Ihren Tabellen in Ihren Word-Dokumenten Leerzeichen links, oben, rechts und unten am Inhalt zu schaffen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie die Formatierung Ihrer Tabellen an Ihre spezifischen Bedürfnisse anpassen.