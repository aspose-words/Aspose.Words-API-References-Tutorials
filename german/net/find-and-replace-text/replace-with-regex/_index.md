---
title: Durch Regex ersetzen
linktitle: Durch Regex ersetzen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine auf regulären Ausdrücken basierende Textersetzung in einem Word-Dokument durchführen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-with-regex/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Durch Regex ersetzen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie Textersetzungen basierend auf bestimmten Mustern durchführen, die durch einen regulären Ausdruck definiert werden.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Ersetzung durch reguläre Ausdrücke beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Methode zum Einfügen der Phrase „traurig, verrückt, schlecht“:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Schritt 3: Konfigurieren der Such- und Ersetzungsoptionen

 Jetzt konfigurieren wir die Such- und Ersetzungsoptionen mithilfe von a`FindReplaceOptions` Objekt. In unserem Beispiel verwenden wir die Standardoptionen:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Schritt 4: Durch regulären Ausdruck ersetzen

 Wir benutzen daS`Range.Replace` Methode zum Durchführen einer Textersetzung mithilfe eines regulären Ausdrucks. In unserem Beispiel verwenden wir den regulären Ausdruck „[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Schritt 5: Speichern des geänderten Dokuments

 Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Beispielquellcode für „Ersetzen durch Regex“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Ersetzung regulärer Ausdrücke mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Durch Regex ersetzen“ von Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung, um ein Dokument zu erstellen, Text einzufügen, die Ersetzung durch einen regulären Ausdruck durchzuführen und das geänderte Dokument zu speichern.
