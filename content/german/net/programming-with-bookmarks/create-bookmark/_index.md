---
title: Lesezeichen im Word-Dokument erstellen
linktitle: Lesezeichen im Word-Dokument erstellen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Lesezeichen in Word-Dokumenten erstellen und Lesezeichenvorschauebenen in einer PDF-Datei festlegen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/create-bookmark/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Lesezeichen erstellen“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Mit dieser Funktion können Sie Lesezeichen in einem Dokument erstellen und Lesezeichenvorschauebenen in einer PDF-Ausgabedatei angeben.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen des Dokuments und des Generators

 Bevor wir Lesezeichen erstellen können, müssen wir ein Dokument und einen Dokument-Builder erstellen. Dazu verwenden wir`Document` Und`DocumentBuilder` Objekte:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Hauptlesezeichen erstellen

 Wir benutzen das`StartBookmark` Methode zum Starten eines Hauptlesezeichens und des`EndBookmark` Methode, um es zu beenden. Dazwischen können wir Text und andere Lesezeichen hinzufügen:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Fügen Sie hier weitere Lesezeichen oder Text hinzu.

builder. EndBookmark("My Bookmark");
```

## Schritt 3: Verschachtelte Lesezeichen erstellen

 Wir können auch verschachtelte Lesezeichen innerhalb eines Hauptlesezeichens erstellen. Wir verwenden die gleiche`StartBookmark` Und`EndBookmark` Methoden zum Erstellen und Beenden verschachtelter Lesezeichen:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Schritt 4: Festlegen der Lesezeichenvorschauebenen in der PDF-Ausgabedatei

 Wir benutzen das`PdfSaveOptions` Objekt, um die Lesezeichenvorschauebenen in der Ausgabe-PDF-Datei anzugeben. Wir verwenden das`BookmarksOutlineLevels` Eigentum

  um Hauptlesezeichen und verschachtelte Lesezeichen mit ihren jeweiligen Ebenen hinzuzufügen:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Beispielquellcode zum Erstellen eines Lesezeichens mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Erstellung von Lesezeichen mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

### FAQs

#### F: Was sind die Voraussetzungen für die Verwendung der Funktion „Lesezeichen erstellen“ in Aspose.Words für .NET?

A: Um die Funktion „Lesezeichen erstellen“ in Aspose.Words für .NET verwenden zu können, müssen Sie über Grundkenntnisse der Sprache C# verfügen. Sie benötigen außerdem eine .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

#### F: Wie erstelle ich ein Dokument in Aspose.Words für .NET?

 A: Um ein Dokument in Aspose.Words für .NET zu erstellen, können Sie das`Document` Klasse. Hier ist ein Beispielcode:

```csharp
Document doc = new Document();
```

#### F: Wie erstelle ich mit Aspose.Words für .NET ein Hauptlesezeichen in einem Dokument?

 A: Um ein Hauptlesezeichen in einem Dokument mit Aspose.Words für .NET zu erstellen, können Sie das`StartBookmark` Methode, um das Lesezeichen zu starten, Text oder andere Lesezeichen hinzuzufügen, dann verwenden Sie die` EndBookmark` um es zu beenden. Hier ist ein Beispielcode:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### F: Wie erstelle ich mit Aspose.Words für .NET ein verschachteltes Lesezeichen innerhalb eines Hauptlesezeichens?

 A: Um ein verschachteltes Lesezeichen innerhalb eines Hauptlesezeichens mit Aspose.Words für .NET zu erstellen, können Sie dasselbe verwenden`StartBookmark` Und`EndBookmark` Methoden zum Starten und Beenden des verschachtelten Lesezeichens. Hier ist ein Beispielcode:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### F: Wie gebe ich mit Aspose.Words für .NET Lesezeichenvorschauebenen in einer Ausgabe-PDF an?

 A: Um Lesezeichenvorschauebenen in einer Ausgabe-PDF mit Aspose.Words für .NET festzulegen, können Sie den`PdfSaveOptions` Klasse und die`BookmarksOutlineLevels` Eigenschaft. Sie können Hauptlesezeichen und verschachtelte Lesezeichen mit ihren jeweiligen Ebenen hinzufügen. Hier ist ein Beispielcode:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### F: Wie speichere ich ein Dokument, nachdem ich mit Aspose.Words für .NET Lesezeichen erstellt habe?

 A: Um ein Dokument zu speichern, nachdem Sie Lesezeichen mit Aspose.Words für .NET erstellt haben, können Sie das`Save` Methode der`Document` Objekt, das den Zieldateipfad angibt. Hier ist ein Beispielcode:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### F: Wie gebe ich mit Aspose.Words für .NET Lesezeichenvorschauebenen in einer Ausgabe-PDF an?

 A: Um Lesezeichenvorschauebenen in einer Ausgabe-PDF mit Aspose.Words für .NET festzulegen, können Sie den`PdfSaveOptions` Klasse und die`BookmarksOutlineLevels` Eigenschaft. Sie können Hauptlesezeichen und verschachtelte Lesezeichen mit ihren jeweiligen Ebenen hinzufügen. Hier ist ein Beispielcode:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### F: Wie erstelle ich mit Aspose.Words für .NET verschachtelte Lesezeichen innerhalb eines Hauptlesezeichens?

 A: Um verschachtelte Lesezeichen innerhalb eines Hauptlesezeichens mit Aspose.Words für .NET zu erstellen, können Sie dasselbe verwenden`StartBookmark` Und`EndBookmark` Methoden zum Starten und Beenden verschachtelter Lesezeichen. Achten Sie darauf, das übergeordnete Lesezeichen als Parameter anzugeben, wenn Sie die`StartBookmark` Methode. Hier ist ein Beispielcode:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Lesezeichen ein?

 A: Um Text in ein Lesezeichen mit Aspose.Words für .NET einzufügen, können Sie den`Write` Methode der`DocumentBuilder`Objekt, das den hinzuzufügenden Text angibt. Hier ist ein Beispielcode:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### F: Wie erstelle ich mit Aspose.Words für .NET ein Hauptlesezeichen in einem Dokument?

 A: Um ein Hauptlesezeichen in einem Dokument mit Aspose.Words für .NET zu erstellen, können Sie das`StartBookmark` Methode zum Starten des Lesezeichens und der`EndBookmark` Methode, um es zu beenden. Hier ist ein Beispielcode:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```