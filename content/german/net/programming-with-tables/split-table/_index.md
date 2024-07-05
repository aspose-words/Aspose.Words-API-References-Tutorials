---
title: Geteilte Tabelle
linktitle: Geteilte Tabelle
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument aufteilen.
type: docs
weight: 10
url: /de/net/programming-with-tables/split-table/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument aufteilt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie eine Tabelle aus einer bestimmten Zeile in Ihren Word-Dokumenten aufteilen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Dokument einlegen
Um die Textverarbeitung mit dem Dokument zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis und geben Sie den richtigen Dateinamen an.

## Schritt 3: Den Tisch aufteilen
Als nächstes teilen wir die Tabelle ab einer bestimmten Zeile. Verwenden Sie den folgenden Code:

```csharp
// Abrufen der ersten Tabelle
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Bestimmung der Linie, ab der die Tabelle geteilt werden soll
Row row = firstTable.Rows[2];

// Erstellen Sie einen neuen Container für die geteilte Tabelle
Table table = (Table)firstTable.Clone(false);

// Fügen Sie den Container nach der Originaltabelle ein
firstTable.ParentNode.InsertAfter(table, firstTable);

// Fügen Sie einen Pufferabsatz hinzu, um den Abstand zwischen den Tabellen beizubehalten
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Verschieben von Zeilen aus der Originaltabelle in die geteilte Tabelle
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Hier verwenden wir das Dokument, um die erste Tabelle aus dem Dokumentknoten abzurufen. Dann bestimmen wir die Zeile, ab der wir die Tabelle teilen möchten, in diesem Beispiel ist es die dritte Zeile (Index 2). Anschließend erstellen wir einen neuen Container, indem wir die ursprüngliche Tabelle klonen und ihn dann nach der ursprünglichen Tabelle einfügen. Wir fügen außerdem einen Pufferabsatz ein, um einen Abstand zwischen den beiden Tabellen einzuhalten. Anschließend verschieben wir Zeilen aus der ursprünglichen Tabelle mithilfe einer do-while-Schleife in die geteilte Tabelle, bis wir die angegebene Zeile erreichen.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir retten die

  Dokument, das mit der geteilten Tabelle geändert wurde. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispiel-Quellcode für Split Table mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Wir werden die Tabelle in der dritten Zeile (einschließlich) teilen.
Row row = firstTable.Rows[2];
// Erstellen Sie einen neuen Container für die geteilte Tabelle.
Table table = (Table) firstTable.Clone(false);
// Setzen Sie den Behälter nach dem Original ein.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Fügen Sie einen Pufferabsatz hinzu, um sicherzustellen, dass die Tabellen getrennt bleiben.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument aufteilt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen ab einer bestimmten Zeile in Ihren Word-Dokumenten problemlos aufteilen.