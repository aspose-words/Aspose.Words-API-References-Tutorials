---
title: Metazeichen im Suchmuster
linktitle: Metazeichen im Suchmuster
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Metazeichen im Suchmuster verwenden, um Word-Dokumente zu bearbeiten.
type: docs
weight: 10
url: /de/net/find-and-replace-text/meta-characters-in-search-pattern/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Metazeichen im Suchmuster“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Mit dieser Funktion können Sie spezielle Metazeichen verwenden, um erweiterte Such- und Ersetzungsvorgänge in Word-Dokumenten durchzuführen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

 Bevor wir Metazeichen im Suchmuster verwenden, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch Instanziieren eines`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Und`Write` Methoden zum Einfügen von zwei Textzeilen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Schritt 3: Suchen und Ersetzen von Text durch Metazeichen

 Nun verwenden wir die`Range.Replace` Funktion zum Suchen und Ersetzen von Text mithilfe eines Suchmusters, das spezielle Metazeichen enthält. In unserem Beispiel ersetzen wir die Phrase "Dies ist Zeile 1&pDies ist Zeile 2" durch "Diese Zeile wird ersetzt" mithilfe der`&p` Metazeichen zur Darstellung eines Absatzumbruchs:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Schritt 4: Seitenumbruch im Dokument einfügen

 Um die Verwendung eines weiteren Metazeichens zu veranschaulichen, fügen wir einen Seitenumbruch in das Dokument ein, indem wir das`InsertBreak` Methode mit dem`BreakType.PageBreak` Parameter. Wir bewegen den Cursor zunächst vom`DocumentBuilder` bis zum Ende des Dokuments, dann fügen wir den Seitenumbruch und eine neue Textzeile ein:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Schritt 5: Suchen und durch ein anderes Metazeichen ersetzen

 Nun führen wir eine weitere Suche und Ersetzung durch, und zwar mit dem`&m` Metazeichen zur Darstellung eines Seitenumbruchs. Wir ersetzen den Satz „Dies ist Zeile 1&mDies ist Zeile 2“ durch „Der Seitenumbruch wird durch neuen Text ersetzt.“:

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Schritt 6: Speichern des bearbeiteten Dokuments

Abschließend speichern wir das geänderte Dokument in einem angegebenen Verzeichnis mit dem`Save` Methode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Beispielquellcode für Meta Characters In Search Pattern mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Verwendung von Metazeichen im Suchmuster mit Aspose.Words für .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Der Pfad zum Dokumentverzeichnis.
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

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie Metazeichen im Suchmuster von Aspose.Words für .NET verwendet werden. Wir folgten einer Schritt-für-Schritt-Anleitung, um ein Dokument zu erstellen, Text einzufügen, Suchen und Ersetzen mit speziellen Metazeichen durchzuführen, Seitenumbrüche einzufügen und das bearbeitete Dokument zu speichern.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Metazeichen im Suchmuster“ in Aspose.Words für .NET?

A: Mit der Funktion „Metazeichen im Suchmuster“ in Aspose.Words für .NET können Sie spezielle Metazeichen verwenden, um erweiterte Suchvorgänge und Ersetzungen in Word-Dokumenten durchzuführen. Mit diesen Metazeichen können Sie Absatzumbrüche, Abschnittsumbrüche, Seitenumbrüche und andere spezielle Elemente in Ihrem Suchmuster darstellen.

#### F: Wie erstelle ich in Aspose.Words für .NET ein neues Dokument?

 A: Bevor Sie Metazeichen in der Suchvorlage verwenden können, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies können Sie tun, indem Sie ein`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Und`Write` Methoden zum Einfügen von zwei Textzeilen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### F: Wie kann ich mit Aspose.Words für .NET Text mit Metazeichen in einem Dokument suchen und ersetzen?

 A: Um Text mit Metazeichen zu suchen und zu ersetzen, können Sie die`Range.Replace` Methode. In unserem Beispiel ersetzen wir den Satz "Dies ist Zeile 1&pDies ist Zeile 2" durch "Diese Zeile wird ersetzt" mit der`&p` Metazeichen zur Darstellung eines Absatzumbruchs:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### F: Wie füge ich mit Aspose.Words für .NET einen Seitenumbruch in ein Dokument ein?

A: Um die Verwendung eines weiteren Metazeichens zu veranschaulichen, fügen wir einen Seitenumbruch in das Dokument ein, indem wir das`InsertBreak` Methode mit dem`BreakType.PageBreak` Parameter. Wir bewegen den Cursor zunächst vom`DocumentBuilder` bis zum Ende des Dokuments, dann fügen wir den Seitenumbruch und eine neue Textzeile ein:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### F: Wie kann ich mit Aspose.Words für .NET in einem Dokument nach einem anderen Metazeichen suchen und es ersetzen?

 A: Wir führen nun eine weitere Suche und Ersetzung durch, und zwar mit dem`&m` Metazeichen zur Darstellung eines Seitenumbruchs. Wir ersetzen den Satz „Dies ist Zeile 1&mDies ist Zeile 2“ durch „Der Seitenumbruch wird durch neuen Text ersetzt.“:

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

 A: Wenn Sie Änderungen am Dokument vorgenommen haben, können Sie es in einem angegebenen Verzeichnis speichern. Dazu verwenden Sie den`Save` Methode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```