---
title: Formatierung auf Zellen und Zeilen aus Stil erweitern
linktitle: Formatierung auf Zellen und Zeilen aus Stil erweitern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erweitern der Formatierung auf Zellen und Zeilen aus einem Tabellenstil mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, um die Formatierung von Zellen und Zeilen aus einem Stil mithilfe von Aspose.Words für .NET zu erweitern. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie mit Aspose.Words für .NET Tabellenformatierungen auf bestimmte Zellen und Zeilen in Ihren Word-Dokumenten anwenden.


## Schritt 1: Dokumentverzeichnis festlegen
Zunächst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Hier befindet sich Ihr Word-Dokument. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Vorhandenes Dokument laden
 Als nächstes müssen Sie das vorhandene Word-Dokument in eine Instanz des`Document` Klasse.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Schritt 3: Gehen Sie zur ersten Zelle der ersten Tabelle
 Zunächst müssen wir zur ersten Zelle der ersten Tabelle im Dokument navigieren. Wir verwenden die`GetChild()`Und`FirstRow.FirstCell` Methoden, um den Verweis auf die erste Zelle zu erhalten.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Schritt 4: Anfängliche Zellenformatierung anzeigen
Vor dem Aufklappen der Styles der Tabelle zeigen wir die aktuelle Hintergrundfarbe der Zelle an. Diese sollte leer sein, da die aktuelle Formatierung im Style der Tabelle hinterlegt ist.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Schritt 5: Tabellenstile zur direkten Formatierung erweitern
 Nun erweitern wir die Tabellenstile um die direkte Formatierung über die`ExpandTableStylesToDirectFormatting()` Methode.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Schritt 6: Zellenformatierung nach Stilerweiterung anzeigen
Nun zeigen wir die Hintergrundfarbe der Zelle nach dem Erweitern der Tabellenstile an. Es soll eine blaue Hintergrundfarbe aus dem Tabellenstil übernommen werden.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Beispielquellcode zum Erweitern der Formatierung auf Zellen und Zeilen aus dem Stil mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Holen Sie sich die erste Zelle der ersten Tabelle im Dokument.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Drucken Sie zuerst die Farbe der Zellenschattierung.
	// Dies sollte leer sein, da die aktuelle Schattierung im Tabellenstil gespeichert ist.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Drucken Sie nun die Zellenschattierung, nachdem Sie die Tabellenstile erweitert haben.
	// Aus dem Tabellenstil hätte eine blaue Hintergrundmusterfarbe angewendet werden sollen.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Words für .NET die Formatierung eines Tabellenstils auf Zellen und Zeilen erweitern. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Formatierung im Tabellenstil ganz einfach auf bestimmte Zellen und Zeilen in Ihren Word-Dokumenten anwenden. Aspose.Words bietet eine leistungsstarke und flexible API zum Bearbeiten und Formatieren von Tabellen in Ihren Dokumenten. Mit diesem Wissen können Sie das Layout und die Präsentation Ihrer Word-Dokumente weiter anpassen.