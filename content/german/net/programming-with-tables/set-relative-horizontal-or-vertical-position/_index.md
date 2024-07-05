---
title: Relative horizontale oder vertikale Position festlegen
linktitle: Relative horizontale oder vertikale Position festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die relative horizontale oder vertikale Position einer Tabelle in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET die relative horizontale oder vertikale Position einer Tabelle in einem Word-Dokument einstellt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie die relative horizontale oder vertikale Position Ihrer Tabelle in Ihren Word-Dokumenten einstellen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Dokument einlegen
Um die Textverarbeitung mit dem Dokument zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis und geben Sie den richtigen Dateinamen an.

## Schritt 3: Festlegen der relativen Position der Tabelle
Als nächstes legen wir die relative horizontale oder vertikale Position der Tabelle fest. Verwenden Sie den folgenden Code:

```csharp
// Abrufen der Tabelle
Table table = doc.FirstSection.Body.Tables[0];

//Definition der relativen horizontalen Position des Tisches
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definieren Sie die relative vertikale Position der Tabelle
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Hier verwenden wir das Dokument, um die erste Tabelle aus dem Hauptteil des ersten Abschnitts abzurufen. Als nächstes legen wir die relative horizontale Position der Tabelle mit dem`HorizontalAnchor` Eigenschaft mit dem`RelativeHorizontalPosition.Column` Wert. Ebenso legen wir die relative vertikale Position der Tabelle mit dem`VerticalAnchor` Eigenschaft mit dem`RelativeVerticalPosition.Page` Wert.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit der definierten relativen Position der Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode zum Festlegen der relativen horizontalen oder vertikalen Position mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die relative horizontale oder vertikale Position einer Tabelle in einem Word-Dokument einstellt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie diese relative Position auf Ihre Tabellen in Ihren Word-Dokumenten anwenden.