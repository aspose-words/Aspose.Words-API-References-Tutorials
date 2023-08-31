---
title: Ändern Sie die Zeilenformatierung
linktitle: Ändern Sie die Zeilenformatierung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Ändern der Tabellenzeilenformatierung mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Ändern der Formatierung einer Tabellenzeile mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET Rahmen, Höhe und Zeilenumbruch einer Tabellenzeile in Ihren Word-Dokumenten ändern.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Hier befindet sich Ihr Word-Dokument. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Vorhandenes Dokument laden
 Als nächstes müssen Sie das vorhandene Word-Dokument in eine Instanz von laden`Document` Klasse.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Schritt 3: Greifen Sie auf die zu ändernde Zeile zu
 Um die Formatierung einer Tabellenzeile zu ändern, müssen wir zu der spezifischen Zeile in der Tabelle navigieren. Wir benutzen das`GetChild()` Und`FirstRow` Methoden, um den Verweis auf die erste Zeile der Tabelle abzurufen.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Schritt 4: Zeilenformatierung ändern
 Jetzt können wir die Zeilenformatierung mithilfe der Eigenschaften von ändern`RowFormat` Klasse. Wir können beispielsweise Zeilenränder entfernen, die automatische Höhe festlegen und Zeilenumbrüche zulassen.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Beispielquellcode zum Ändern der Zeilenformatierung mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Rufen Sie die erste Zeile in der Tabelle ab.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Formatierung einer Tabellenzeile mit Aspose.Words für .NET ändert. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Ränder, die Höhe und den Zeilenumbruch von Zeilen in Ihren Tabellen in Ihren Word-Dokumenten ganz einfach anpassen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das visuelle Layout Ihrer Tabellen an Ihre spezifischen Bedürfnisse anpassen.