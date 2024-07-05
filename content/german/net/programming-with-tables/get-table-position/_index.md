---
title: Tabellenposition abrufen
linktitle: Tabellenposition abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Position einer Tabelle in einem Word-Dokument abrufen.
type: docs
weight: 10
url: /de/net/programming-with-tables/get-table-position/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET die Position einer Tabelle in einem Word-Dokument ermittelt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Tabellenpositionierungseigenschaften in Ihren Word-Dokumenten programmgesteuert abrufen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um Words Processing mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");

// Zugriff auf das Array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Ersetzen Sie unbedingt „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis. Stellen Sie außerdem sicher, dass das Dokument die Tabelle enthält, deren Position Sie abrufen möchten.

## Schritt 3: Abrufen der Array-Positionierungseigenschaften
Als nächstes überprüfen wir den Positionierungstyp des Arrays und ermitteln die entsprechenden Positionierungseigenschaften. Verwenden Sie den folgenden Code:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Hier verwenden wir eine Bedingung, um zu prüfen, ob das Array vom Typ float ist. Wenn ja, drucken wir die`RelativeHorizontalAlignment` Und`RelativeVerticalAlignment` Eigenschaften, um die relative horizontale und vertikale Ausrichtung der Tabelle zu erhalten. Andernfalls drucken wir die`Alignment` Eigenschaft, um die Array-Ausrichtung zu erhalten.

### Beispielquellcode für Get Table Position mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Position einer Tabelle in einem Word-Dokument ermittelt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellenpositionierungseigenschaften in Ihren Word-Dokumenten programmgesteuert ermitteln. Mit dieser Funktion können Sie Arrays entsprechend ihrer spezifischen Positionen analysieren und bearbeiten.