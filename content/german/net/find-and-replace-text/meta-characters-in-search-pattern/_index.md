---
title: Metazeichen im Suchmuster
linktitle: Metazeichen im Suchmuster
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Metazeichen im Suchmuster verwenden, um Word-Dokumente zu bearbeiten.
type: docs
weight: 10
url: /de/net/find-and-replace-text/meta-characters-in-search-pattern/
---
In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Metazeichen im Suchmuster“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie spezielle Metazeichen verwenden, um erweiterte Suchen und Ersetzen in Word-Dokumenten durchzuführen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Verwendung von Metazeichen im Suchmuster beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Und`Write` Methoden zum Einfügen von zwei Textzeilen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Schritt 3: Suchen und ersetzen Sie Text durch Metazeichen

 Jetzt werden wir das verwenden`Range.Replace` Funktion zum Suchen und Ersetzen von Text mithilfe eines Suchmusters, das spezielle Metazeichen enthält. In unserem Beispiel ersetzen wir den Ausdruck „Dies ist Zeile 1&pDies ist Zeile 2“ durch „Diese Zeile wird ersetzt“ mithilfe von`&p` Metazeichen zur Darstellung eines Absatzumbruchs:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Schritt 4: Einfügen eines Seitenumbruchs in das Dokument

 Um die Verwendung eines anderen Metazeichens zu veranschaulichen, fügen wir mithilfe von einen Seitenumbruch in das Dokument ein`InsertBreak` Methode mit der`BreakType.PageBreak` Parameter. Wir bewegen zuerst den Cursor von der`DocumentBuilder` ans Ende des Dokuments, dann fügen wir den Seitenumbruch und eine neue Textzeile ein:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Schritt 5: Suchen und ersetzen Sie es durch ein anderes Metazeichen

 Jetzt führen wir eine weitere Suche und Ersetzung mit durch`&m` Metazeichen zur Darstellung eines Seitenumbruchs. Wir ersetzen den Satz „Dies ist Zeile 1&mDies ist Zeile 2“ durch „Der Seitenumbruch wird durch neuen Text ersetzt.“ :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Schritt 6: Speichern des bearbeiteten Dokuments

Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Beispielquellcode für Metazeichen im Suchmuster mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung von Metazeichen im Suchmuster mit Aspose.Words für .NET zu demonstrieren:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie Metazeichen im Suchmuster von Aspose.Words für .NET verwendet werden. Wir folgten einer Schritt-für-Schritt-Anleitung zum Erstellen eines Dokuments, zum Einfügen von Text, zum Suchen und Ersetzen mithilfe spezieller Metazeichen, zum Einfügen von Seitenumbrüchen und zum Speichern des bearbeiteten Dokuments.

### FAQs

#### F: Was ist die Funktion „Metazeichen im Suchmuster“ in Aspose.Words für .NET?

A: Mit der Funktion „Metazeichen im Suchmuster“ in Aspose.Words für .NET können Sie spezielle Metazeichen verwenden, um erweiterte Suchen und Ersetzungen in Word-Dokumenten durchzuführen. Mit diesen Metazeichen können Sie Absatzumbrüche, Abschnittsumbrüche, Seitenumbrüche und andere spezielle Elemente in Ihrem Suchmuster darstellen.

#### F: Wie erstelle ich ein neues Dokument in Aspose.Words für .NET?

 A: Bevor Sie Metazeichen in der Suchvorlage verwenden, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Und`Write` Methoden zum Einfügen von zwei Textzeilen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### F: Wie kann ich mit Aspose.Words für .NET Text in einem Dokument suchen und durch Metazeichen ersetzen?

 A: Um Text durch Metazeichen zu suchen und zu ersetzen, können Sie die verwenden`Range.Replace` Methode. In unserem Beispiel ersetzen wir den Ausdruck „Dies ist Zeile 1&pDies ist Zeile 2“ durch „Diese Zeile wird ersetzt“ mithilfe von`&p` Metazeichen zur Darstellung eines Absatzumbruchs:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### F: Wie füge ich mit Aspose.Words für .NET einen Seitenumbruch in ein Dokument ein?

A: Um die Verwendung eines anderen Metazeichens zu veranschaulichen, fügen wir mit dem einen Seitenumbruch in das Dokument ein`InsertBreak` Methode mit der`BreakType.PageBreak` Parameter. Wir bewegen zuerst den Cursor von der`DocumentBuilder` ans Ende des Dokuments, dann fügen wir den Seitenumbruch und eine neue Textzeile ein:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### F: Wie kann ich mit Aspose.Words für .NET in einem Dokument suchen und es durch ein anderes Metazeichen ersetzen?

 A: Wir werden jetzt ein weiteres Suchen und Ersetzen mit durchführen`&m` Metazeichen zur Darstellung eines Seitenumbruchs. Wir ersetzen den Satz „Dies ist Zeile 1&mDies ist Zeile 2“ durch „Der Seitenumbruch wird durch neuen Text ersetzt.“ :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

 A: Sobald Sie Änderungen am Dokument vorgenommen haben, können Sie es mithilfe von in einem angegebenen Verzeichnis speichern`Save` Methode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```