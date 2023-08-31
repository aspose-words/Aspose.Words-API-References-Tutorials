---
title: Geteilter Tisch
linktitle: Geteilter Tisch
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument teilen.
type: docs
weight: 10
url: /de/net/programming-with-tables/split-table/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument aufteilt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, eine Tabelle aus einer bestimmten Zeile in Ihren Word-Dokumenten aufzuteilen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments
Gehen Sie folgendermaßen vor, um die Textverarbeitung mit dem Dokument zu starten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen und den korrekten Dateinamen angeben.

## Schritt 3: Den Tisch teilen
Als nächstes werden wir die Tabelle von einer bestimmten Zeile trennen. Verwenden Sie den folgenden Code:

```csharp
// Rufen Sie die erste Tabelle ab
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Bestimmung der Zeile, von der aus die Tabelle geteilt werden soll
Row row = firstTable.Rows[2];

// Erstellen Sie einen neuen Container für die geteilte Tabelle
Table table = (Table)firstTable.Clone(false);

// Fügen Sie den Container nach der Originaltabelle ein
firstTable.ParentNode.InsertAfter(table, firstTable);

// Fügen Sie einen Pufferabsatz hinzu, um den Abstand zwischen den Tabellen aufrechtzuerhalten
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Verschieben Sie Zeilen aus der Originaltabelle in die geteilte Tabelle
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Hier verwenden wir das Dokument, um die erste Tabelle aus dem Dokumentknoten abzurufen. Dann bestimmen wir die Zeile, ab der wir die Tabelle teilen möchten, in diesem Beispiel ist es die dritte Zeile (Index 2). Anschließend erstellen wir einen neuen Container, indem wir die Originaltabelle klonen und ihn dann nach der Originaltabelle einfügen. Wir fügen außerdem einen Pufferabsatz hinzu, um den Abstand zwischen den beiden Tabellen aufrechtzuerhalten. Dann verschieben wir mithilfe einer Do-While-Schleife Zeilen aus der Originaltabelle in die geteilte Tabelle, bis wir die angegebene Zeile erreichen.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir das speichern

  Dokument, das mit der geteilten Tabelle geändert wurde. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Split Table mit Aspose.Words für .NET 

```csharp
//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Wir werden die Tabelle in der dritten Zeile (einschließlich) teilen.
Row row = firstTable.Rows[2];
// Erstellen Sie einen neuen Container für die geteilte Tabelle.
Table table = (Table) firstTable.Clone(false);
// Setzen Sie den Behälter nach dem Original ein.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Fügen Sie einen Pufferabsatz hinzu, um sicherzustellen, dass die Tabellen auseinander bleiben.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument teilt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen problemlos ab einer bestimmten Zeile in Ihren Word-Dokumenten aufteilen.