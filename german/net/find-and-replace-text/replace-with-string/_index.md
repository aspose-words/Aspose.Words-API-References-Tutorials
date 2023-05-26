---
title: Durch Zeichenfolge ersetzen
linktitle: Durch Zeichenfolge ersetzen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text durch eine Zeichenfolge in einem Word-Dokument ersetzen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-with-string/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Durch Zeichenfolge ersetzen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie Textersetzungen basierend auf einer bestimmten Zeichenfolge in einem Word-Dokument durchführen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

Bevor wir mit der Zeichenfolgenersetzung beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

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

## Schritt 3: Durch eine Zeichenfolge ersetzen

 Wir benutzen das`Range.Replace` Methode zum Ersetzen von Text durch eine Zeichenfolge. In unserem Beispiel ersetzen wir alle Vorkommen des Wortes „sad“ durch „bad“, indem wir das verwenden`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Schritt 4: Speichern des bearbeiteten Dokuments

 Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Beispielquellcode für „Ersetzen durch String“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung des Ersetzens durch eine Zeichenfolge mit Aspose.Words für .NET zu veranschaulichen:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Durch Zeichenfolge ersetzen“ von Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung zum Erstellen eines Dokuments, zum Einfügen von Text, zum Ersetzen durch eine Zeichenfolge und zum Speichern des geänderten Dokuments.
