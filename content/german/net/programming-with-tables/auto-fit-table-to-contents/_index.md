---
title: Tabelle automatisch an Inhalt anpassen
linktitle: Tabelle automatisch an Inhalt anpassen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle automatisch an ihren Inhalt in einem Word-Dokument anpassen.
type: docs
weight: 10
url: /de/net/programming-with-tables/auto-fit-table-to-contents/
---

In diesem Tutorial lernen wir, wie man Aspose.Words für .NET verwendet, um eine Tabelle mit C# automatisch an ihren Inhalt in einem Word-Dokument anzupassen. Wir werden den Prozess des Schreibens von Code Schritt für Schritt durchgehen, um diese Funktionalität zu erreichen. Am Ende dieses Tutorials haben Sie ein klares Verständnis dafür, wie Sie Tabellen in Word-Dokumenten programmgesteuert bearbeiten können.

## Schritt 1: Einrichten des Projekts
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden Sie das Word-Dokument
Um Words Processing mit der Tabelle zu starten, müssen wir das Word-Dokument laden, das die Tabelle enthält. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Tables.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokument ersetzen.

## Schritt 3: Auf die Tabelle zugreifen und sie automatisch an den Inhalt anpassen
Als nächstes müssen wir auf die Tabelle im Dokument zugreifen und das Auto-Fit-Verhalten anwenden. Verwenden Sie den folgenden Code:

```csharp
// Zugriff auf die Tabelle
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Automatisches Anpassen der Tabelle an ihren Inhalt
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Hier konvertieren wir den ersten Kindknoten vom Typ`Table` aus dem Dokument und verwenden Sie dann die`AutoFit` Methode mit dem`AutoFitToContents` Verhalten, um die Tabellenbreite an den Inhalt anzupassen.

## Schritt 4: Speichern Sie das geänderte Dokument
Zum Schluss müssen wir das geänderte Dokument mit der automatisch angepassten Tabelle speichern. Verwenden Sie dazu den folgenden Code:

```csharp
// Speichern des geänderten Dokuments
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für „Tabelle automatisch an Inhalt anpassen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle automatisch an ihren Inhalt in einem Word-Dokument anpasst. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen in Ihren Word-Dokumenten programmgesteuert bearbeiten. Auf diese Weise können Sie die Tabellenbreite dynamisch an den Inhalt anpassen und so ein professionelleres und optisch ansprechenderes Dokument erstellen.