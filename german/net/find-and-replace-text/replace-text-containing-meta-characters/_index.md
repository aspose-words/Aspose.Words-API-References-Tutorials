---
title: Word ersetzt Text, der Metazeichen enthält
linktitle: Word ersetzt Text, der Metazeichen enthält
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text ersetzen, der Metazeichen in Word-Dokumenten enthält.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-text-containing-meta-characters/
---
In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Word Text mit Metazeichen ersetzen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie Textteile in einem Dokument ersetzen, die bestimmte Metazeichen enthalten.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Textersetzung durch Metazeichen beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Methode zum Einfügen mehrerer Textabsätze in verschiedene Abschnitte:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## Schritt 3: Konfigurieren der Such- und Ersetzungsoptionen

 Jetzt konfigurieren wir die Such- und Ersetzungsoptionen mithilfe von a`FindReplaceOptions` Objekt. In unserem Beispiel stellen wir die Ausrichtung der ersetzten Absätze auf „Zentriert“:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Schritt 4: Ersetzen von Text, der Metazeichen enthält

 Wir benutzen das`Range.Replace`Methode zum Ersetzen von Text, der Metazeichen enthält. In unserem Beispiel ersetzen wir jedes Vorkommen des Wortes „Abschnitt“, gefolgt von einem Absatzumbruch, durch dasselbe Wort, gefolgt von mehreren Bindestrichen und einem neuen Absatzumbruch:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Schritt 5: Ersetzen eines benutzerdefinierten Text-Tags

 Wir nutzen auch die`Range.Replace` Methode zum Ersetzen eines benutzerdefinierten "{insert-section}„ Text-Tag durch einen Abschnittsumbruch. In unserem Beispiel ersetzen wir „{insert-section}" mit „&b“, um einen Abschnittsumbruch einzufügen:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Schritt 6: Speichern des bearbeiteten Dokuments

 Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Beispielquellcode zum Ersetzen von Text mit Metazeichen mithilfe von Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Textersetzung mit Metazeichen mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Verdoppeln Sie jeden Absatzumbruch nach dem Wort „Abschnitt“, fügen Sie eine Art Unterstreichung hinzu und zentrieren Sie ihn.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Fügen Sie einen Abschnittswechsel anstelle eines benutzerdefinierten Text-Tags ein.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text mit Metazeichen ersetzen“ von Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung zum Erstellen eines Dokuments, zum Einfügen von Text, zum Ersetzen von Text mit Metazeichen und zum Speichern des geänderten Dokuments.

### FAQs

#### F: Was ist die Funktion „Text mit Metazeichen ersetzen“ in Aspose.Words für .NET?

A: Mit der Funktion „Text mit Metazeichen ersetzen“ in Aspose.Words für .NET können Sie Textteile in einem Dokument ersetzen, die bestimmte Metazeichen enthalten. Mit dieser Funktion können Sie erweiterte Ersetzungen in Ihrem Dokument unter Berücksichtigung von Metazeichen durchführen.

#### F: Wie erstelle ich ein neues Dokument in Aspose.Words für .NET?

 A: Bevor Sie die Funktion „Text mit Metazeichen ersetzen“ verwenden, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Methode zum Einfügen mehrerer Textabsätze in verschiedene Abschnitte:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### F: Wie konfiguriere ich Such- und Ersetzungsoptionen in Aspose.Words für .NET?

 A: Jetzt konfigurieren wir die Such- und Ersetzungsoptionen mithilfe von a`FindReplaceOptions` Objekt. In unserem Beispiel stellen wir die Ausrichtung der ersetzten Absätze auf „Zentriert“:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### F: Wie ersetze ich Text, der Metazeichen enthält, in einem Dokument mit Aspose.Words für .NET?

 A: Wir verwenden das`Range.Replace` Methode zum Ersetzen von Text, der Metazeichen enthält. In unserem Beispiel ersetzen wir jedes Vorkommen des Wortes „Abschnitt“, gefolgt von einem Absatzumbruch, durch dasselbe Wort, gefolgt von mehreren Bindestrichen und einem neuen Absatzumbruch:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### F: Wie ersetze ich mit Aspose.Words für .NET ein benutzerdefiniertes Text-Tag, das Metazeichen enthält, in einem Dokument?

 A: Wir verwenden auch die`Range.Replace` Methode zum Ersetzen eines benutzerdefinierten "{insert-section}„ Text-Tag durch einen Abschnittsumbruch. In unserem Beispiel ersetzen wir „{insert-section}" mit „&b“, um einen Abschnittsumbruch einzufügen:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

 A: Sobald Sie Änderungen am Dokument vorgenommen haben, können Sie es mithilfe von in einem angegebenen Verzeichnis speichern`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```