---
title: Holen Sie sich die schwebende Tischposition
linktitle: Holen Sie sich die schwebende Tischposition
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Position schwebender Tabellen in einem Word-Dokument ermitteln.
type: docs
weight: 10
url: /de/net/programming-with-tables/get-floating-table-position/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET die Position einer schwebenden Tabelle in einem Word-Dokument ermitteln. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, die Positionierungseigenschaften einer schwebenden Tabelle in Ihren Word-Dokumenten programmgesteuert abzurufen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Laden des Dokuments und Zugriff auf die Tabellen
Um mit der Arbeit mit Tabellen zu beginnen, müssen wir das Dokument laden, das sie enthält, und auf sie zugreifen. Folge diesen Schritten:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Laden Sie das Dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen. Stellen Sie außerdem sicher, dass das Dokument schwebende Tabellen enthält.

## Schritt 3: Positionierungseigenschaften für schwebende Tabellen abrufen
Als Nächstes durchlaufen wir alle Tabellen im Dokument und ermitteln die Positionierungseigenschaften für schwebende Tabellen. Verwenden Sie den folgenden Code:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Wenn es sich bei dem Array um einen Floating-Typ handelt, werden seine Positionierungseigenschaften ausgegeben.
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

 Hier verwenden wir a`foreach` Schleife, um alle Arrays im Dokument zu durchlaufen. Wir prüfen, ob das Array vom Float-Typ ist, indem wir Folgendes überprüfen`TextWrapping` Eigentum. Wenn ja, drucken wir die Positionierungseigenschaften der Tabelle aus, z. B. horizontaler Anker, vertikaler Anker, absolute horizontale und vertikale Abstände, Überlappungsberechtigung, absoluter horizontaler Abstand und relative vertikale Ausrichtung.
 
### Beispielquellcode für „Get Floating Table Position“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Wenn es sich bei der Tabelle um einen Floating-Typ handelt, drucken Sie ihre Positionierungseigenschaften aus.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Position einer schwebenden Tabelle in einem Word-Dokument ermittelt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie die Positionierungseigenschaften von Floating-Tabellen in Ihren Word-Dokumenten programmgesteuert abrufen. Mit dieser Funktion können Sie schwebende Tabellen entsprechend Ihren spezifischen Anforderungen analysieren und bearbeiten.