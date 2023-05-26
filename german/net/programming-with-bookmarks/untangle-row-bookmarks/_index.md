---
title: Zeilenlesezeichen entwirren
linktitle: Zeilenlesezeichen entwirren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie verschachtelte Zeilenlesezeichen entwirren, um bestimmte Zeilen zu entfernen, ohne dass sich dies auf andere Lesezeichen auswirkt.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/untangle-row-bookmarks/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Zeilenlesezeichen entwirren“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Diese Funktion ermöglicht es, die Enden von Lesezeichen von Zeilen in die gleiche Zeile wie die Anfänge von Lesezeichen zu setzen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Laden des Dokuments

 Wir benutzen das`Document` Klasse zum Laden des vorhandenen Dokuments aus einer Datei:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Schritt 2: Linien-Lesezeichen entwirren

 Wir benutzen das`Untangle` Funktion zum Entwirren von Lesezeichen aus Zeilen. Diese Funktion führt die benutzerdefinierte Aufgabe aus, die Enden der Lesezeichenzeilen in derselben Zeile zu platzieren, in der das Lesezeichen beginnt:

```csharp
Untangle(doc);
```

## Schritt 3: Zeile per Lesezeichen löschen

 Wir benutzen das`DeleteRowByBookmark` Funktion zum Löschen einer bestimmten Zeile anhand ihres Lesezeichens:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Schritt 4: Überprüfen Sie die Integrität anderer Lesezeichen

Wir stellen sicher, dass die anderen Lesezeichen nicht beschädigt wurden, indem wir prüfen, ob das Ende des Lesezeichens noch vorhanden ist:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Beispielquellcode für Untangle Row Bookmarks mit Aspose.Words für .NET**

Hier ist der vollständige Beispielquellcode zum Entwirren von Lesezeichen aus Zeilen mithilfe von Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Dadurch wird die benutzerdefinierte Aufgabe ausgeführt, die Enden der Zeilenlesezeichen in derselben Zeile wie die Lesezeichenanfänge zu platzieren.
	Untangle(doc);

	// Jetzt können wir ganz einfach Zeilen mit einem Lesezeichen löschen, ohne die Lesezeichen einer anderen Zeile zu beschädigen.
	DeleteRowByBookmark(doc, "ROW2");

	// Dies dient lediglich der Überprüfung, ob das andere Lesezeichen nicht beschädigt wurde.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Zeilenlesezeichen entwirren“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um Zeilenlesezeichen zu entwirren und eine bestimmte Zeile zu löschen, ohne andere Lesezeichen zu beschädigen.