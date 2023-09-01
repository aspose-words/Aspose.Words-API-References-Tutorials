---
title: Tabelle aus HTML einfügen
linktitle: Tabelle aus HTML einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle aus HTML in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/programming-with-tables/insert-table-from-html/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle aus HTML in ein Word-Dokument einfügen. Wir folgen einer Schritt-für-Schritt-Anleitung, um den Code zu verstehen und diese Funktion zu implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, Tabellen aus HTML programmgesteuert in Ihre Word-Dokumente einzufügen.

## Schritt 1: Projekteinrichtung
1. Starten Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.Words für .NET-Bibliothek hinzu.

## Schritt 2: Erstellen des Dokuments und Initialisieren des Dokumentengenerators
Um die Textverarbeitung mit dem Dokument und dem Dokumentengenerator zu starten, gehen Sie folgendermaßen vor:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung
Document doc = new Document();

// Initialisieren Sie den Dokumentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 3: Einfügen der Tabelle aus HTML
Als nächstes fügen wir die Tabelle mithilfe von HTML-Code in das Dokument ein. Verwenden Sie den folgenden Code:

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

 Hier verwenden wir die`InsertHtml` Methode des Document Builders, um den HTML-Code einzufügen, der die Tabelle enthält. Der angegebene HTML-Code erstellt eine Tabelle mit zwei Zeilen und zwei Zellen in jeder Zeile. Sie können den Inhalt der Tabelle anpassen, indem Sie den HTML-Code entsprechend Ihren Anforderungen ändern.

## Schritt 4: Speichern des geänderten Dokuments
Abschließend müssen wir das geänderte Dokument mit der aus HTML eingefügten Tabelle speichern. Verwenden Sie den folgenden Code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen für das Ausgabedokument angeben.

### Beispielquellcode für „Tabelle aus HTML einfügen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Beachten Sie, dass AutoFitSettings nicht für aus HTML eingefügte Tabellen gilt.
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine Tabelle aus HTML in ein Word-Dokument einfügt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code implementieren, können Sie Tabellen aus HTML programmgesteuert in Ihre Word-Dokumente einfügen. Mit dieser Funktion können Sie Tabellendaten aus HTML-Quellen konvertieren und in Ihre Word-Dokumente importieren.
