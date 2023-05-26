---
title: Einfaches Suchen und Ersetzen
linktitle: Einfaches Suchen und Ersetzen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine einfache Suche/Ersetzung in einem Word-Dokument durchführen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/simple-find-replace/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Einfache Suche und Ersetzung“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie eine einfache Textersetzung durchführen, indem Sie nach einer bestimmten Zeichenfolge suchen und diese durch eine andere Zeichenfolge in einem Word-Dokument ersetzen.

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
