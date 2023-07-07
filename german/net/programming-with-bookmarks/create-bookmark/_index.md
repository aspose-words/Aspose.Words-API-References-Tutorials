---
title: Lesezeichen erstellen
linktitle: Lesezeichen erstellen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Lesezeichen in einem Dokument erstellen und Lesezeichen-Vorschauebenen in einer PDF-Datei festlegen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/create-bookmark/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Lesezeichen erstellen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie Lesezeichen in einem Dokument erstellen und Lesezeichen-Vorschauebenen in einer PDF-Ausgabedatei festlegen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Dokument und Generator erstellen

 Bevor wir Lesezeichen erstellen, müssen wir ein Dokument und einen Dokument-Builder mit erstellen`Document` Und`DocumentBuilder` Objekte:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Erstellen des Hauptlesezeichens

 Wir benutzen das`StartBookmark` Methode zum Starten eines Hauptlesezeichens und der`EndBookmark` Methode, um es zu beenden. Zwischendurch können wir Text und andere Lesezeichen hinzufügen:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Fügen Sie hier weitere Lesezeichen oder Text hinzu.

builder. EndBookmark("My Bookmark");
```

## Schritt 3: Verschachtelte Lesezeichen erstellen

 Wir können auch verschachtelte Lesezeichen innerhalb eines Hauptlesezeichens erstellen. Wir verwenden das Gleiche`StartBookmark` Und`EndBookmark` Methoden zum Erstellen und Beenden verschachtelter Lesezeichen:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Schritt 4: Festlegen der Lesezeichenvorschauebenen in der Ausgabe-PDF-Datei

 Wir benutzen das`PdfSaveOptions` -Objekt, um die Lesezeichenvorschauebenen in der Ausgabe-PDF-Datei anzugeben. Wir benutzen das`BookmarksOutlineLevels` Eigentum

  So fügen Sie Hauptlesezeichen und verschachtelte Lesezeichen mit ihren jeweiligen Ebenen hinzu:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Beispielquellcode für „Lesezeichen erstellen“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um das Erstellen von Lesezeichen mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Lesezeichen erstellen“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung zum Erstellen von Lesezeichen in einem Dokument und zum Festlegen von Lesezeichenvorschauebenen in einer PDF-Ausgabedatei befolgt.