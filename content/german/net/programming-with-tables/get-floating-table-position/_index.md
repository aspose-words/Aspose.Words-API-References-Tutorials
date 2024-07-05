---
title: Schwebende Tabellenposition abrufen
linktitle: Schwebende Tabellenposition abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Position schwebender Tabellen in einem Word-Dokument abrufen.
type: docs
weight: 10
url: /de/net/programming-with-tables/get-floating-table-position/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET die Position einer schwebenden Tabelle in einem Word-Dokument ermitteln. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie die Positionierungseigenschaften einer schwebenden Tabelle in Ihren Word-Dokumenten programmgesteuert abrufen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabellen
Um die Textverarbeitung mit Tabellen zu starten, müssen wir das Dokument, das sie enthält, laden und darauf zugreifen. Folgen Sie diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Ersetzen Sie unbedingt „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis. Stellen Sie außerdem sicher, dass das Dokument schwebende Tabellen enthält.

## Schritt 3: Abrufen der Positionierungseigenschaften für schwebende Tabellen
Als Nächstes durchlaufen wir alle Tabellen im Dokument und ermitteln die Positionierungseigenschaften der schwebenden Tabellen. Verwenden Sie den folgenden Code:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Wenn das Array ein Floating-Typ ist, drucken Sie seine Positionierungseigenschaften.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Hier verwenden wir eine`foreach` loop, um alle Arrays im Dokument zu durchlaufen. Wir prüfen, ob das Array vom Typ float ist, indem wir den`TextWrapping` Eigenschaft. Wenn ja, drucken wir die Positionierungseigenschaften der Tabelle, wie horizontalen Anker, vertikalen Anker, absolute horizontale und vertikale Abstände, Überlappungsberechtigung, absoluten horizontalen Abstand und vertikale relative Ausrichtung.
 
### Beispielquellcode zum Abrufen der Floating Table Position mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Wenn es sich bei der Tabelle um eine schwebende Tabelle handelt, drucken Sie ihre Positionierungseigenschaften.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Position einer schwebenden Tabelle in einem Word-Dokument ermittelt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die Positionierungseigenschaften schwebender Tabellen in Ihren Word-Dokumenten programmgesteuert ermitteln. Mit dieser Funktion können Sie schwebende Tabellen entsprechend Ihren spezifischen Anforderungen analysieren und bearbeiten.