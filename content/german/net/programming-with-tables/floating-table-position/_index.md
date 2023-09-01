---
title: Schwebende Tischposition
linktitle: Schwebende Tischposition
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle schwebend in einem Word-Dokument positionieren.
type: docs
weight: 10
url: /de/net/programming-with-tables/floating-table-position/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle an einer schwebenden Position in einem Word-Dokument positionieren. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, die Position und Ausrichtung schwebender Tabellen in Ihren Word-Dokumenten programmgesteuert zu steuern.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um die Textverarbeitung mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Zugriff auf das Array
Table table = doc.FirstSection.Body.Tables[0];
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen. Stellen Sie außerdem sicher, dass das Dokument eine Tabelle enthält, die in einer schwebenden Position positioniert wird.

## Schritt 3: Positionierung des Schwebebretts
Als Nächstes positionieren wir die Tabelle mithilfe der von Aspose.Words für .NET bereitgestellten Eigenschaften in einer schwebenden Position. Verwenden Sie den folgenden Code:

```csharp
// Positionierung des schwebenden Tisches
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Hier verwenden wir die`AbsoluteHorizontalDistance` Eigenschaft, um den absoluten horizontalen Abstand der Tabelle vom linken Rand der Seite festzulegen. Wir nutzen auch die`RelativeVerticalAlignment` -Eigenschaft, um die relative vertikale Ausrichtung der Tabelle zum umgebenden Inhalt festzulegen.

## Schritt 4: Speichern des geänderten Dokuments
Schließlich müssen wir das geänderte Dokument speichern, wobei die Tabelle in einer schwebenden Position positioniert ist. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für Floating Table Position mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man eine Tabelle mit Aspose.Words für .NET an einer schwebenden Position in einem Word-Dokument positioniert. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die Position und Ausrichtung von schwebenden Tabellen in Ihren Word-Dokumenten programmgesteuert steuern.