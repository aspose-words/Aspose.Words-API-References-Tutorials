---
title: Zeilenformat Umbruch über mehrere Seiten deaktivieren
linktitle: Zeilenformat Umbruch über mehrere Seiten deaktivieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Zeilenumbruch für eine Tabelle über mehrere Seiten in einem Word-Dokument deaktivieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/row-format-disable-break-across-pages/
---

In diesem Tutorial erfahren Sie, wie Sie den Zeilenumbruch einer mehrseitigen Tabelle in einem Word-Dokument mit Aspose.Words für .NET deaktivieren. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie den Zeilenumbruch für alle Zeilen Ihrer Tabelle in Ihren Word-Dokumenten deaktivieren.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Dokument einlegen
Um die Textverarbeitung mit dem Dokument zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis und geben Sie den richtigen Dateinamen an.

## Schritt 3: Zeilenumbruch in der Tabelle deaktivieren
Als nächstes deaktivieren wir den Zeilenumbruch für alle Zeilen in der Tabelle. Verwenden Sie den folgenden Code:

```csharp
// Abrufen der Tabelle
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Zeilenumbruch für alle Zeilen in der Tabelle deaktivieren
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Hier verwenden wir das Dokument, um die erste Tabelle abzurufen und durchlaufen dann alle Zeilen in der Tabelle mithilfe einer foreach-Schleife. Innerhalb der Schleife deaktivieren wir den Zeilenumbruch für jede Zeile, indem wir den`RowFormat.AllowBreakAcrossPages`Eigentum an`false`.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit deaktiviertem Tabellenzeilenumbruch speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode für Zeilenformat „Umbruch über mehrere Seiten deaktivieren“ mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
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