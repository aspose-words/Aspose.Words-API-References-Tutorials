---
title: Word ersetzt Text, der Metazeichen enthält
linktitle: Word ersetzt Text, der Metazeichen enthält
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text mit Metazeichen in Word-Dokumenten ersetzen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-text-containing-meta-characters/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie man die Funktion „Text mit Metazeichen ersetzen“ in der Aspose.Words-Bibliothek für .NET verwendet. Mit dieser Funktion können Sie Textteile in einem Dokument ersetzen, die bestimmte Metazeichen enthalten.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

 Bevor wir mit der Verwendung des Metazeichen-Textersatzes beginnen, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Methode zum Einfügen mehrerer Textabsätze in verschiedene Abschnitte:

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

## Schritt 3: Konfigurieren der Optionen zum Suchen und Ersetzen

 Nun konfigurieren wir die Suchen- und Ersetzen-Optionen mit einem`FindReplaceOptions` Objekt. In unserem Beispiel setzen wir die Ausrichtung der ersetzten Absätze auf „Zentriert“:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Schritt 4: Ersetzen von Text mit Metazeichen

 Wir benutzen das`Range.Replace`Methode zum Ersetzen von Text mit Metazeichen. In unserem Beispiel ersetzen wir jedes Vorkommen des Wortes „Absatz“, gefolgt von einem Absatzumbruch, durch dasselbe Wort, gefolgt von mehreren Bindestrichen und einem neuen Absatzumbruch:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Schritt 5: Ersetzen eines benutzerdefinierten Text-Tags

 Wir verwenden auch die`Range.Replace` Methode zum Ersetzen einer benutzerdefinierten "{insert-section}" Text-Tag mit einem Abschnittsumbruch. In unserem Beispiel ersetzen wir "{insert-section}" mit "&b", um einen Abschnittsumbruch einzufügen:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Schritt 6: Speichern des bearbeiteten Dokuments

Abschließend speichern wir das geänderte Dokument in einem angegebenen Verzeichnis mit dem`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Beispielquellcode zum Ersetzen von Text mit Metazeichen mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Verwendung von Textersetzung mit Metazeichen mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

	// Fügen Sie einen Abschnittsumbruch anstelle eines benutzerdefinierten Texttags ein.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text mit Metazeichen ersetzen“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um ein Dokument zu erstellen, Text einzufügen, Text mit Metazeichen zu ersetzen und das geänderte Dokument zu speichern.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Text ersetzen, der Metazeichen enthält“ in Aspose.Words für .NET?

A: Mit der Funktion „Text mit Metazeichen ersetzen“ in Aspose.Words für .NET können Sie Textteile in einem Dokument ersetzen, die bestimmte Metazeichen enthalten. Mit dieser Funktion können Sie erweiterte Ersetzungen in Ihrem Dokument unter Berücksichtigung von Metazeichen durchführen.

#### F: Wie erstelle ich in Aspose.Words für .NET ein neues Dokument?

 A: Bevor Sie die Funktion „Text mit Metazeichen ersetzen“ verwenden, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies können Sie tun, indem Sie ein`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Methode zum Einfügen mehrerer Textabsätze in verschiedene Abschnitte:

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

 A: Nun konfigurieren wir die Suchen- und Ersetzen-Optionen mit einem`FindReplaceOptions` Objekt. In unserem Beispiel setzen wir die Ausrichtung der ersetzten Absätze auf „Zentriert“:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### F: Wie ersetze ich mit Aspose.Words für .NET Text in einem Dokument, der Metazeichen enthält?

 A: Wir verwenden die`Range.Replace` Methode zum Ersetzen von Text, der Metazeichen enthält. In unserem Beispiel ersetzen wir jedes Vorkommen des Wortes „Absatz“, gefolgt von einem Absatzumbruch, durch dasselbe Wort, gefolgt von mehreren Bindestrichen und einem neuen Absatzumbruch:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### F: Wie ersetze ich mit Aspose.Words für .NET ein benutzerdefiniertes Text-Tag, das Metazeichen in einem Dokument enthält?

 A: Wir verwenden auch die`Range.Replace` Methode zum Ersetzen einer benutzerdefinierten "{insert-section}" Text-Tag mit einem Abschnittsumbruch. In unserem Beispiel ersetzen wir "{insert-section}" mit "&b", um einen Abschnittsumbruch einzufügen:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### F: Wie speichere ich ein bearbeitetes Dokument in Aspose.Words für .NET?

 A: Wenn Sie Änderungen am Dokument vorgenommen haben, können Sie es in einem angegebenen Verzeichnis speichern. Dazu verwenden Sie den`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```