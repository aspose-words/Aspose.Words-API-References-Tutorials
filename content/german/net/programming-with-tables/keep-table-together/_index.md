---
title: Tisch zusammenhalten
linktitle: Tisch zusammenhalten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zusammenhalten.
type: docs
weight: 10
url: /de/net/programming-with-tables/keep-table-together/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zusammenhält. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie eine Tabelle intakt halten, ohne dass sie sich auf mehrere Seiten in Ihren Word-Dokumenten verteilt.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Dokument laden und Tabelle abrufen
Um Words Processing mit der Tabelle zu starten, müssen wir das Dokument laden und die Tabelle abrufen, die wir zusammenhalten möchten. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Abrufen der Tabelle
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Option „KeepWithNext“ aktivieren
Um die Tabelle zusammenzuhalten und zu verhindern, dass sie sich über mehrere Seiten erstreckt, müssen wir die Option „KeepWithNext“ für jeden Absatz in der Tabelle aktivieren, mit Ausnahme der letzten Absätze der letzten Tabellenzeile. Verwenden Sie den folgenden Code:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Hier durchlaufen wir jede Zelle der Tabelle und aktivieren die Option „KeepWithNext“ für jeden Absatz in der Zelle mit Ausnahme der letzten Absätze der letzten Zeile der Tabelle.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit der zusammengehaltenen Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispiel-Quellcode für Keep Table Together mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Wir müssen KeepWithNext für jeden Absatz in der Tabelle aktivieren, um zu verhindern, dass er über eine Seite umbricht.
	// mit Ausnahme der letzten Absätze in der letzten Zeile der Tabelle.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zusammenhält. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie eine Tabelle intakt halten und verhindern, dass sie sich in Ihren Dokumenten auf mehrere Seiten verteilt. Diese Funktion gibt Ihnen mehr Kontrolle über das Erscheinungsbild und Layout Ihrer Tabellen in Ihren Dokumenten.