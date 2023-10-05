---
title: Zeilenformat Deaktivieren Sie den Seitenumbruch
linktitle: Zeilenformat Deaktivieren Sie den Seitenumbruch
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Zeilenumbruch für eine Tabelle über mehrere Seiten in einem Word-Dokument deaktivieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/row-format-disable-break-across-pages/
---

In diesem Tutorial erfahren Sie, wie Sie den Zeilenumbruch einer mehrseitigen Tabelle in einem Word-Dokument mithilfe von Aspose.Words für .NET deaktivieren. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, den Zeilenumbruch für alle Zeilen in Ihrer Tabelle in Ihren Word-Dokumenten zu deaktivieren.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments
Gehen Sie folgendermaßen vor, um die Textverarbeitung mit dem Dokument zu starten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen und den korrekten Dateinamen angeben.

## Schritt 3: Tabellenzeilenumbruch deaktivieren
Als Nächstes deaktivieren wir den Zeilenumbruch für alle Zeilen in der Tabelle. Verwenden Sie den folgenden Code:

```csharp
// Rufen Sie die Tabelle ab
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Deaktivieren Sie den Zeilenumbruch für alle Zeilen in der Tabelle
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Hier verwenden wir das Dokument, um die erste Tabelle abzurufen und durchlaufen dann alle Zeilen in der Tabelle mithilfe einer foreach-Schleife. Innerhalb der Schleife deaktivieren wir den Zeilenumbruch für jede Zeile, indem wir festlegen`RowFormat.AllowBreakAcrossPages`Eigentum zu`false`.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir das geänderte Dokument mit deaktiviertem Tabellenzeilenumbruch speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für das Zeilenformat „Deaktivieren Sie den Seitenumbruch mit Aspose.Words für .NET“. 

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Deaktivieren Sie den Seitenumbruch für alle Zeilen in der Tabelle.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den Zeilenumbruch einer mehrseitigen Tabelle in einem Word-Dokument mit Aspose.Words für .NET deaktiviert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie diese Deaktivierung auf Ihre Tabellen in Ihren Word-Dokumenten anwenden.