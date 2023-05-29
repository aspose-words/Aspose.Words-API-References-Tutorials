---
title: In Tabellenzelle verschieben
linktitle: In Tabellenzelle verschieben
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von „In Tabellenzelle verschieben“ in Aspose.Words für .NET
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-table-cell/
---

In diesem Beispiel führen wir Sie Schritt für Schritt durch die Verwendung der Funktion „In Tabellenzelle verschieben“ von Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes. Mit dieser Funktion können Sie in einer Tabelle in einem Word-Dokument durch bestimmte Zellen navigieren und diese bearbeiten. Führen Sie die folgenden Schritte aus, um diese Funktionalität in Ihre Anwendung zu integrieren.

## Schritt 1: Laden Sie das Dokument mit der Tabelle

Zuerst müssen wir das Dokument laden, das die Tabelle enthält, in die wir die Zelle verschieben möchten. Verwenden Sie den folgenden Code, um diesen Schritt auszuführen:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Dieser Code lädt das angegebene Dokument (ersetzen Sie „MyDir + „Tables.docx“)„“ mit dem tatsächlichen Pfad Ihres Dokuments, das die Tabelle enthält).

## Schritt 2: Verschieben Sie den DocumentBuilder in eine bestimmte Tabellenzelle

Als Nächstes verschieben wir den DocumentBuilder in eine bestimmte Tabellenzelle. Verwenden Sie den folgenden Code, um diesen Schritt auszuführen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

 Dieser Code erstellt einen DocumentBuilder aus dem vorhandenen Dokument und bewegt dann den Cursor vom DocumentBuilder zur angegebenen Tabellenzelle. Schließlich fügt es mithilfe des DocumentBuilders Inhalt zu dieser Zelle hinzu`Write()` Methode.

## Schritt 3: Überprüfen Sie das Ergebnis

Sie können nun überprüfen, ob die Verschiebung in die Tabellenzelle erfolgreich war. Verwenden Sie den folgenden Code, um diesen Schritt auszuführen:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Dieser Code überprüft, ob die angegebene Zelle tatsächlich die aktuelle Zelle des DocumentBuilder ist. Außerdem wird überprüft, ob der vom DocumentBuilder hinzugefügte Inhalt korrekt in der Tabellenzelle gespeichert wurde.

Das ist alles ! Sie haben nun verstanden, wie Sie die Funktion „In Tabellenzelle verschieben“ von Aspose.Words für .NET mithilfe des bereitgestellten Quellcodes verwenden. Sie können diese Funktionalität jetzt in Ihre eigene Anwendung integrieren und bestimmte Tabellenzellen in Word-Dokumenten bearbeiten.


### Beispielquellcode zum Verschieben in eine Tabellenzelle mit Aspose.Words für .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Verschieben Sie den Builder in Zeile 3, Zelle 4 der ersten Tabelle.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```
