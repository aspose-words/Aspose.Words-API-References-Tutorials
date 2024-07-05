---
title: Schwebende Tischposition
linktitle: Schwebende Tischposition
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle in einer schwebenden Position in einem Word-Dokument positionieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/floating-table-position/
---

In diesem Tutorial lernen wir, wie man Aspose.Words für .NET verwendet, um eine Tabelle in einem Word-Dokument schwebend zu positionieren. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie die Position und Ausrichtung schwebender Tabellen in Ihren Word-Dokumenten programmgesteuert steuern.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um Words Processing mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Zugriff auf das Array
Table table = doc.FirstSection.Body.Tables[0];
```

Ersetzen Sie unbedingt „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis. Stellen Sie außerdem sicher, dass das Dokument eine Tabelle enthält, die in einer schwebenden Position positioniert wird.

## Schritt 3: Positionierung des Schwimmbretts
Als Nächstes positionieren wir die Tabelle in einer schwebenden Position mithilfe der von Aspose.Words für .NET bereitgestellten Eigenschaften. Verwenden Sie den folgenden Code:

```csharp
// Positionierung des schwebenden Tisches
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Hier verwenden wir die`AbsoluteHorizontalDistance` Eigenschaft, um den absoluten horizontalen Abstand der Tabelle vom linken Rand der Seite festzulegen. Wir verwenden auch die`RelativeVerticalAlignment` -Eigenschaft, um die relative vertikale Ausrichtung der Tabelle zum umgebenden Inhalt festzulegen.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit der schwebenden Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
// Speichern des geänderten Dokuments
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispiel-Quellcode für Floating Table Position mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle in einem Word-Dokument schwebend positioniert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die Position und Ausrichtung schwebender Tabellen in Ihren Word-Dokumenten programmgesteuert steuern.