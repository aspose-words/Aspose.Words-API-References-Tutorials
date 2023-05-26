---
title: Tabelle erstellen
linktitle: Tabelle erstellen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/build-table/
---

In diesem Schritt-für-Schritt-Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Handbuchs werden Sie in der Lage sein, mithilfe der DocumentBuilder-Klasse eine Tabelle mit benutzerdefinierter Formatierung und Inhalt zu erstellen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Starten Sie die Tabelle
Als nächstes verwenden Sie die StartTable-Methode der DocumentBuilder-Klasse, um mit dem Aufbau der Tabelle zu beginnen:

```csharp
Table table = builder.StartTable();
```

## Schritt 3: Zellen einfügen und Inhalt hinzufügen
Jetzt können Sie Zellen in die Tabelle einfügen und ihnen Inhalte hinzufügen, indem Sie die Methoden InsertCell und Write der DocumentBuilder-Klasse verwenden. Passen Sie die Zellenformatierung nach Bedarf an:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Schritt 4: Beenden Sie die Reihe
Nachdem Sie den Zellen der ersten Zeile Inhalt hinzugefügt haben, verwenden Sie die EndRow-Methode der DocumentBuilder-Klasse, um die Zeile zu beenden:

```csharp
builder.EndRow();
```

## Schritt 5: Passen Sie die Zeilenformatierung an
Sie können die Formatierung einer Zeile anpassen, indem Sie Eigenschaften der RowFormat- und CellFormat-Objekte festlegen:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Schritt 6: Beenden Sie den Tisch
Um die Tabelle zu vervollständigen, verwenden Sie die EndTable-Methode der DocumentBuilder-Klasse:

```csharp
builder.EndTable();
```

### Beispielquellcode zum Erstellen einer Tabelle mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Erstellen einer Tabelle mit Aspose.Words für .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument erstellen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt Tabellen mit benutzerdefinierter Formatierung erstellen.