---
title: In eine Tabellenzelle im Word-Dokument verschieben
linktitle: In eine Tabellenzelle im Word-Dokument verschieben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „In Tabellenzelle verschieben“ in der Word-Dokumentfunktion von Aspose.Words für .NET
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-table-cell/
---
In diesem Beispiel führen wir Sie Schritt für Schritt durch die Verwendung der Funktion „In Tabellenzelle verschieben“ in Word-Dokumenten von Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes. Mit dieser Funktion können Sie in einer Tabelle in einem Word-Dokument durch bestimmte Zellen navigieren und diese bearbeiten. Führen Sie die folgenden Schritte aus, um diese Funktionalität in Ihre Anwendung zu integrieren.

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

## Abschluss

In diesem Beispiel haben wir die Funktion „In Tabellenzelle verschieben“ von Aspose.Words für .NET untersucht. Wir haben gelernt, wie man ein Dokument mit einer Tabelle lädt, den DocumentBuilder in eine bestimmte Tabellenzelle verschiebt und dieser Zelle Inhalte hinzufügt. Diese Funktion bietet Entwicklern leistungsstarke Tools zum programmgesteuerten Navigieren und Bearbeiten bestimmter Zellen in Word-Dokumenttabellen mithilfe von Aspose.Words für .NET. Es kann eine wertvolle Ergänzung Ihrer Anwendung für die dynamische Verarbeitung von Word-Dokumenten und die Verwaltung von Tabelleninhalten sein.

### FAQs zum Verschieben in eine Tabellenzelle in einem Word-Dokument

#### F: Was ist der Zweck der Funktion „In Tabellenzelle verschieben“ in Aspose.Words für .NET?

A: Mit der Funktion „In Tabellenzelle verschieben“ in Aspose.Words für .NET können Entwickler programmgesteuert zu bestimmten Zellen in einer Tabelle in einem Word-Dokument navigieren und diese bearbeiten. Es bietet die Möglichkeit, Inhalte innerhalb einer bestimmten Zelle einzufügen, zu ändern oder zu löschen.

#### F: Wie verschiebe ich den DocumentBuilder in eine bestimmte Tabellenzelle in einem Word-Dokument?

A: Um den DocumentBuilder in eine bestimmte Tabellenzelle in einem Word-Dokument zu verschieben, können Sie die MoveToCell-Methode der DocumentBuilder-Klasse verwenden. Diese Methode verwendet die Indizes der Zielzeile und -zelle in der Tabelle als Parameter und platziert den Cursor am Anfang dieser Zelle.

#### F: Kann ich Inhalte hinzufügen oder ändern, nachdem ich mit der Funktion „In Tabellenzelle verschieben“ zu einer bestimmten Tabellenzelle verschoben habe?

A: Ja, sobald der DocumentBuilder mit MoveToCell an der gewünschten Tabellenzelle positioniert ist, können Sie verschiedene Methoden der DocumentBuilder-Klasse wie Write, Writeln oder InsertHtml verwenden, um den Inhalt dieser Zelle hinzuzufügen oder zu ändern.

#### F: Wie kann ich überprüfen, ob die Verschiebung in die Tabellenzelle erfolgreich war?

A: Sie können die erfolgreiche Verschiebung in die Tabellenzelle überprüfen, indem Sie die Position des DocumentBuilder-Cursors überprüfen. Sie können beispielsweise den aktuellen Knoten des DocumentBuilder mit der Zelle vergleichen, in die Sie verschieben möchten, und überprüfen, ob der vom DocumentBuilder hinzugefügte Inhalt korrekt in der Tabellenzelle gespeichert wird.