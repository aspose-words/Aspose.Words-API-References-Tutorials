---
title: Legen Sie die relative horizontale oder vertikale Position fest
linktitle: Legen Sie die relative horizontale oder vertikale Position fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die relative horizontale oder vertikale Position einer Tabelle in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET die relative horizontale oder vertikale Position einer Tabelle in einem Word-Dokument festlegen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, die relative horizontale oder vertikale Position Ihrer Tabelle in Ihren Word-Dokumenten festzulegen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments
Gehen Sie folgendermaßen vor, um die Textverarbeitung mit dem Dokument zu starten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen und den korrekten Dateinamen angeben.

## Schritt 3: Einstellen der relativen Position der Tabelle
Als nächstes legen wir die relative horizontale oder vertikale Position der Tabelle fest. Verwenden Sie den folgenden Code:

```csharp
// Rufen Sie die Tabelle ab
Table table = doc.FirstSection.Body.Tables[0];

//Definition der relativen horizontalen Position des Tisches
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definieren Sie die relative vertikale Position der Tabelle
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Hier verwenden wir das Dokument, um die erste Tabelle aus dem Hauptteil des ersten Abschnitts abzurufen. Als nächstes legen wir die relative horizontale Position des Tisches fest`HorizontalAnchor` Eigentum unter Verwendung der`RelativeHorizontalPosition.Column` Wert. Ebenso legen wir die relative vertikale Position des Tisches mit fest`VerticalAnchor` Eigentum unter Verwendung der`RelativeVerticalPosition.Page` Wert.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir das geänderte Dokument mit der definierten relativen Position der Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode zum Festlegen der relativen horizontalen oder vertikalen Position mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die relative horizontale oder vertikale Position einer Tabelle in einem Word-Dokument festlegt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie diese relative Position auf Ihre Tabellen in Ihren Word-Dokumenten anwenden.