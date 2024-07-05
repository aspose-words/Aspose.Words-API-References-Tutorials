---
title: Tabelle aus HTML einfügen
linktitle: Tabelle aus HTML einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle aus HTML in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-tables/insert-table-from-html/
---

In diesem Tutorial lernen wir, wie man mit Aspose.Words für .NET eine Tabelle aus HTML in ein Word-Dokument einfügt. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials können Sie Tabellen aus HTML programmgesteuert in Ihre Word-Dokumente einfügen.

## Schritt 1: Projekt-Setup
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words-Bibliothek für .NET hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentgenerators
Um die Textverarbeitung mit dem Dokument- und Dokumentgenerator zu starten, führen Sie diese Schritte aus:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumenterstellung
Document doc = new Document();

// Initialisieren des Dokumentgenerators
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 3: Einfügen der Tabelle aus HTML
Als nächstes fügen wir die Tabelle per HTML-Code in das Dokument ein. Verwenden Sie dazu den folgenden Code:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Hier verwenden wir die`InsertHtml` Methode des Dokumentgenerators, um das HTML einzufügen, das die Tabelle enthält. Das angegebene HTML erstellt eine Tabelle mit zwei Zeilen und zwei Zellen in jeder Zeile. Sie können den Inhalt der Tabelle anpassen, indem Sie den HTML-Code entsprechend Ihren Anforderungen ändern.

## Schritt 4: Speichern des geänderten Dokuments
Zum Schluss müssen wir das geänderte Dokument mit der aus HTML eingefügten Tabelle speichern. Verwenden Sie dazu den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Achten Sie darauf, den richtigen Pfad und Dateinamen für das Ausgabedokument anzugeben.

### Beispielquellcode zum Einfügen einer Tabelle aus HTML mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Beachten Sie, dass AutoFitSettings nicht auf aus HTML eingefügte Tabellen zutrifft.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle aus HTML in ein Word-Dokument einfügt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen aus HTML programmgesteuert in Ihre Word-Dokumente einfügen. Mit dieser Funktion können Sie tabellarische Daten aus HTML-Quellen in Ihre Word-Dokumente konvertieren und importieren.
