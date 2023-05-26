---
title: Ermitteln Sie den Abstand zwischen dem von der Tabelle umgebenden Text
linktitle: Ermitteln Sie den Abstand zwischen dem von der Tabelle umgebenden Text
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ermitteln des Abstands zwischen Text und einer Tabelle in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, um mit Aspose.Words für .NET den Abstand zwischen umgebendem Text in einer Tabelle zu ermitteln. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET auf die verschiedenen Abstände zwischen einer Tabelle und dem umgebenden Text in Ihren Word-Dokumenten zugreifen können.

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

## Schritt 3: Ermitteln Sie den Abstand zwischen der Tabelle und dem umgebenden Text
 Um den Abstand zwischen der Tabelle und dem umgebenden Text zu ermitteln, müssen wir mithilfe von auf die Tabelle im Dokument zugreifen`GetChild()` Methode und die`NodeType.Table` Eigentum. Anschließend können wir die unterschiedlichen Abstände über die Array-Eigenschaften anzeigen`DistanceTop`, `DistanceBottom`, `DistanceRight` Und`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Beispielquellcode für „Abstand zwischen tabellenumgebendem Text ermitteln“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET den Abstand zwischen umgebendem Text in einer Tabelle ermittelt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach auf die verschiedenen Abstände zwischen einer Tabelle und dem umgebenden Text in Ihren Word-Dokumenten zugreifen. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das Layout Ihrer Tabellen im Verhältnis zum Text analysieren und spezifische Anforderungen erfüllen.