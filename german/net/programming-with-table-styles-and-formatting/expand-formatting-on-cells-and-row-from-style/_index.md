---
title: Erweitern Sie die Formatierung von Zellen und Zeilen im Stil
linktitle: Erweitern Sie die Formatierung von Zellen und Zeilen im Stil
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erweitern der Formatierung auf Zellen und Zeilen aus einem Tabellenstil mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Erweitern der Formatierung auf Zellen und Zeilen aus einem Stil mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.Words für .NET Tabellenformatierungen auf bestimmte Zellen und Zeilen in Ihren Word-Dokumenten anwenden.


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

## Schritt 3: Gehen Sie zur ersten Zelle der ersten Tabelle
 Zunächst müssen wir zur ersten Zelle der ersten Tabelle im Dokument navigieren. Wir benutzen das`GetChild()` Und`FirstRow.FirstCell` Methoden, um den Verweis auf die erste Zelle zu erhalten.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Schritt 4: Anfängliche Zellenformatierung anzeigen
Bevor wir die Stile der Tabelle erweitern, zeigen wir die aktuelle Hintergrundfarbe der Zelle an. Dies sollte leer sein, da die aktuelle Formatierung im Stil der Tabelle gespeichert ist.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Schritt 5: Erweitern Sie Tabellenstile auf Direktformatierung
 Jetzt erweitern wir die Tabellenstile um eine direkte Formatierung mithilfe der Dokumente`ExpandTableStylesToDirectFormatting()` Methode.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Schritt 6: Zellenformatierung nach Stilerweiterung anzeigen
Jetzt zeigen wir die Hintergrundfarbe der Zelle an, nachdem wir die Tabellenstile erweitert haben. Aus dem Tabellenstil sollte eine blaue Hintergrundfarbe übernommen werden.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Beispielquellcode für den Stil „Formatierung von Zellen und Zeilen erweitern“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Rufen Sie die erste Zelle der ersten Tabelle im Dokument ab.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Drucken Sie zunächst die Farbe der Zellschattierung aus.
	// Dies sollte leer sein, da die aktuelle Schattierung im Tabellenstil gespeichert ist.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Drucken Sie nun die Zellschattierung aus, nachdem Sie die Tabellenstile erweitert haben.
	// Aus dem Tabellenstil sollte eine blaue Hintergrundmusterfarbe angewendet werden.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Formatierung aus einem Tabellenstil auf Zellen und Zeilen erweitert. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Formatierung im Tabellenstil ganz einfach auf bestimmte Zellen und Zeilen in Ihren Word-Dokumenten anwenden. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das Layout und die Präsentation Ihrer Word-Dokumente weiter anpassen.