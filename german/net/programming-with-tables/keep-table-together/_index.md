---
title: Halten Sie den Tisch zusammen
linktitle: Halten Sie den Tisch zusammen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zusammenhalten.
type: docs
weight: 10
url: /de/net/programming-with-tables/keep-table-together/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zusammenhält. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, eine Tabelle intakt zu halten, ohne dass sie sich auf mehrere Seiten in Ihren Word-Dokumenten aufteilt.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments und Abrufen der Tabelle
Um mit der Tabelle zu arbeiten, müssen wir das Dokument laden und die Tabelle abrufen, die wir zusammenhalten möchten. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Laden Sie das Dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Rufen Sie die Tabelle ab
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Aktivieren Sie die Option „KeepWithNext“.
Um die Tabelle zusammenzuhalten und zu verhindern, dass sie sich auf mehrere Seiten aufteilt, müssen wir die Option „KeepWithNext“ für jeden Absatz in der Tabelle aktivieren, mit Ausnahme der letzten Absätze der letzten Zeile der Tabelle. Verwenden Sie den folgenden Code:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Hier durchlaufen wir jede Zelle in der Tabelle und aktivieren die Option „KeepWithNext“ für jeden Absatz in der Zelle, mit Ausnahme der letzten Absätze der letzten Zeile in der Tabelle.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit zusammengehaltener Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Keep Table Together mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Wir müssen KeepWithNext für jeden Absatz in der Tabelle aktivieren, um zu verhindern, dass er sich über eine Seite erstreckt.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument zusammenhält. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie eine Tabelle intakt halten und verhindern, dass sie sich über mehrere Seiten in Ihren Dokumenten aufteilt. Mit dieser Funktion haben Sie mehr Kontrolle über das Erscheinungsbild und Layout Ihrer Tabellen in Ihren Dokumenten.