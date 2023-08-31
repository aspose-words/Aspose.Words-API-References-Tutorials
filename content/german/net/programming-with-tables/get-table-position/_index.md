---
title: Tabellenposition abrufen
linktitle: Tabellenposition abrufen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Position einer Tabelle in einem Word-Dokument ermitteln.
type: docs
weight: 10
url: /de/net/programming-with-tables/get-table-position/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET die Position einer Tabelle in einem Word-Dokument ermitteln. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Tabellenpositionierungseigenschaften programmgesteuert in Ihren Word-Dokumenten abzurufen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabelle
Um die Textverarbeitung mit der Tabelle zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Tables.docx");

// Zugriff auf das Array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen. Stellen Sie außerdem sicher, dass das Dokument die Tabelle enthält, deren Position Sie abrufen möchten.

## Schritt 3: Array-Positionierungseigenschaften abrufen
Als Nächstes überprüfen wir den Positionierungstyp des Arrays und ermitteln die entsprechenden Positionierungseigenschaften. Verwenden Sie den folgenden Code:

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

 Hier verwenden wir eine Bedingung, um zu prüfen, ob das Array vom Typ Float ist. Wenn ja, drucken wir das aus`RelativeHorizontalAlignment` Und`RelativeVerticalAlignment` Eigenschaften, um die relative horizontale und vertikale Ausrichtung der Tabelle zu ermitteln. Ansonsten drucken wir das aus`Alignment` Eigenschaft, um die Array-Ausrichtung zu erhalten.

### Beispielquellcode für „Get Table Position“ mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Position einer Tabelle in einem Word-Dokument ermittelt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellenpositionierungseigenschaften in Ihren Word-Dokumenten programmgesteuert abrufen. Mit dieser Funktion können Sie Arrays entsprechend ihrer spezifischen Positionen analysieren und manipulieren.