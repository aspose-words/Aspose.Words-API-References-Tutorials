---
title: Einfaches Suchen und Ersetzen von Text in Word
linktitle: Einfaches Suchen und Ersetzen von Text in Word
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine einfache Textsuche und -ersetzung in einem Word-Dokument durchführen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/simple-find-replace/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie man die einfache Textsuche und -ersetzung in der Aspose.Words-Bibliothek für .NET verwendet. Mit dieser Funktion können Sie eine einfache Textersetzung durchführen, indem Sie nach einer bestimmten Zeichenfolge suchen und diese durch eine andere Zeichenfolge in einem Word-Dokument ersetzen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit dem einfachen Suchen und Ersetzen beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Methode zum Einfügen der Phrase „Hallo_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Schritt 3: Einfache Textersetzung

 Wir benutzen das`Range.Replace` Methode zur einfachen Textersetzung. In unserem Beispiel ersetzen wir alle Vorkommen der Zeichenfolge „_ClientName_ " mit „James Bond“ unter Verwendung der`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Schritt 4: Speichern des bearbeiteten Dokuments

Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Beispielquellcode für Simple Find Replacement mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung des einfachen Suchens und Ersetzens mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Speichern Sie das geänderte Dokument
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Einfaches Suchen und Ersetzen“ von Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein Dokument zu erstellen, Text einzufügen, eine einfache Textersetzung durchzuführen und das bearbeitete Dokument zu speichern.

### FAQs

#### F: Was ist die Funktion zum einfachen Suchen und Ersetzen von Text in Aspose.Words für .NET?

A: Mit der Funktion „Einfaches Suchen und Ersetzen von Text“ in Aspose.Words für .NET können Sie eine einfache Textersetzung in einem Word-Dokument durchführen. Es ermöglicht Ihnen, nach einer bestimmten Zeichenfolge zu suchen und diese durch eine andere Zeichenfolge zu ersetzen. Dies kann nützlich sein, wenn Sie globale Änderungen an einem Dokument vornehmen möchten, z. B. das Ersetzen von Namen, Daten oder anderen Informationen.

#### F: Wie erstelle ich ein neues Dokument in Aspose.Words für .NET?

 A: Bevor Sie die Funktion „Einfacher Text suchen und ersetzen“ verwenden, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Methode zum Einfügen der Phrase „Hallo_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### F: Wie führe ich mit Aspose.Words für .NET eine einfache Textersetzung in einem Dokument durch?

 A: Um eine einfache Textersetzung durchzuführen, können Sie die verwenden`Range.Replace` Methode. In unserem Beispiel ersetzen wir alle Vorkommen der Zeichenfolge „_ClientName_ " mit „James Bond“ unter Verwendung der`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

 A: Sobald Sie die Textersetzung durchgeführt haben, können Sie das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis speichern`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```