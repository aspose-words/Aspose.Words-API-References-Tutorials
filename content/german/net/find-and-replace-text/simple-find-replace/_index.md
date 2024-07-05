---
title: Einfaches Suchen und Ersetzen von Text in Word
linktitle: Einfaches Suchen und Ersetzen von Text in Word
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine einfache Textsuche und -ersetzung in einem Word-Dokument durchführen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/simple-find-replace/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie man die Funktion „Einfaches Suchen und Ersetzen von Text“ in der Aspose.Words-Bibliothek für .NET verwendet. Mit dieser Funktion können Sie einen einfachen Textersatz durchführen, indem Sie nach einer bestimmten Zeichenfolge suchen und diese durch eine andere Zeichenfolge in einem Word-Dokument ersetzen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

 Bevor wir mit dem einfachen Suchen und Ersetzen beginnen, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Methode zum Einfügen der Phrase "Hallo_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Schritt 3: Einfacher Textersatz

 Wir benutzen das`Range.Replace` Methode, um einfache Textersetzungen durchzuführen. In unserem Beispiel ersetzen wir alle Vorkommen der Zeichenfolge "_ClientName_ " mit "James Bond" unter Verwendung der`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Schritt 4: Speichern des bearbeiteten Dokuments

Abschließend speichern wir das geänderte Dokument in einem angegebenen Verzeichnis mit dem`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Beispielquellcode für Simple Find Replace mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Verwendung der einfachen Suchen- und Ersetzungsfunktion mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Speichern des geänderten Dokuments
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Simple Find Replace“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um ein Dokument zu erstellen, Text einzufügen, einen einfachen Textersatz durchzuführen und das bearbeitete Dokument zu speichern.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Einfacher Text suchen und ersetzen“ in Aspose.Words für .NET?

A: Mit der Funktion „Einfaches Suchen und Ersetzen von Text“ in Aspose.Words für .NET können Sie einfache Textersetzungen in einem Word-Dokument durchführen. Sie können damit nach einer bestimmten Zeichenfolge suchen und diese durch eine andere Zeichenfolge ersetzen. Dies kann nützlich sein, wenn Sie globale Änderungen an einem Dokument vornehmen möchten, z. B. Namen, Daten oder andere Informationen ersetzen möchten.

#### F: Wie erstelle ich in Aspose.Words für .NET ein neues Dokument?

 A: Bevor Sie die Funktion „Suchen und Ersetzen von einfachem Text“ verwenden können, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies können Sie tun, indem Sie`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Methode zum Einfügen der Phrase "Hallo_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### F: Wie führe ich mit Aspose.Words für .NET einen einfachen Textersatz in einem Dokument durch?

 A: Um einen einfachen Textaustausch durchzuführen, können Sie den`Range.Replace` Methode. In unserem Beispiel ersetzen wir alle Vorkommen der Zeichenfolge "_ClientName_ " mit "James Bond" unter Verwendung der`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

 A: Sobald Sie den Text ersetzt haben, können Sie das geänderte Dokument in einem angegebenen Verzeichnis speichern. Dazu verwenden Sie den`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```