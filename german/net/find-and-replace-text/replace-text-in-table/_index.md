---
title: Ersetzen Sie Text in der Tabelle
linktitle: Ersetzen Sie Text in der Tabelle
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text in einer Tabelle in einem Word-Dokument ersetzen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-text-in-table/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Text in Tabelle ersetzen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie bestimmten Text in einer Tabelle in einem Word-Dokument suchen und ersetzen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Laden Sie das Dokument

 Bevor wir mit der Textersetzung in einer Tabelle beginnen, müssen wir das Dokument in Aspose.Words für .NET laden. Dies kann mit der erfolgen`Document` Klasse und Angabe des Dokumentdateipfads:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Schritt 2: Greifen Sie auf das Board zu

 Sobald das Dokument geladen ist, müssen wir zu der Tabelle navigieren, in der wir die Textersetzung durchführen möchten. In unserem Beispiel verwenden wir die`GetChild` Methode mit der`NodeType.Table` Parameter, um die erste Tabelle im Dokument abzurufen:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Schritt 3: Textersetzung durchführen

 Jetzt verwenden wir die`Range.Replace` Methode zum Durchführen der Textersetzung im Array. In unserem Beispiel ersetzen wir alle Vorkommen des Wortes „Karotten“ durch „Eier“, indem wir das verwenden`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung. Zusätzlich ersetzen wir in der letzten Zelle der letzten Zeile der Tabelle den Wert „50“ durch „20“:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Schritt 4: Speichern Sie das bearbeitete Dokument

 Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words für .NET Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein Dokument zu laden, auf die Tabelle zuzugreifen, die Textersetzung durchzuführen und das geänderte Dokument zu speichern.

### Beispielquellcode für „Text in Tabelle ersetzen“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Textersetzung in einer Tabelle mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in Tabelle ersetzen“ von Aspose verwendet wird.
