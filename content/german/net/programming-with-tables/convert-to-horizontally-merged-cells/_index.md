---
title: In horizontal verbundene Zellen konvertieren
linktitle: In horizontal verbundene Zellen konvertieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Tabellenzellen in horizontal verbundene Zellen in einem Word-Dokument konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET Tabellenzellen in horizontal verbundene Zellen in einem Word-Dokument umwandelt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Tabellenzellen in Ihren Word-Dokumenten programmgesteuert bearbeiten.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um Words Processing mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Zugriff auf das Array
Table table = doc.FirstSection.Body.Tables[0];
```

Ersetzen Sie unbedingt „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis. Stellen Sie außerdem sicher, dass das Dokument eine Tabelle mit horizontal verbundenen Zellen enthält.

## Schritt 3: In horizontal verbundene Zellen umwandeln
 Als nächstes konvertieren wir die Tabellenzellen in horizontal verbundene Zellen mit dem`ConvertToHorizontallyMergedCells()` Methode. Verwenden Sie den folgenden Code:

```csharp
// In horizontal verbundene Zellen konvertieren
table. ConvertToHorizontallyMergedCells();
```

 Hier nennen wir einfach die`ConvertToHorizontallyMergedCells()` Methode im Array, um die Konvertierung durchzuführen.

### Beispielquellcode zum Konvertieren in horizontal verbundene Zellen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Zusammengeführte Zellen verfügen jetzt über entsprechende Zusammenführungskennzeichen.
	table.ConvertToHorizontallyMergedCells();
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Tabellenzellen in einem Word-Dokument mit Aspose.Words für .NET in horizontal verbundene Zellen umwandelt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellenzellen in Ihren Word-Dokumenten programmgesteuert bearbeiten. Mit dieser Funktion können Sie Ihre Daten in einer Tabelle flexibel und personalisiert verwalten und organisieren.