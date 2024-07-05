---
title: Text in Feldern ignorieren
linktitle: Text in Feldern ignorieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Text in Feldern ignorieren“ von Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/find-and-replace-text/ignore-text-inside-fields/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Text in Feldern ignorieren“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Diese Funktion ist nützlich, wenn wir beim Bearbeiten von Dokumenten den Text in den Feldern ignorieren möchten.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

 Bevor wir mit der Textbearbeitung in Feldern beginnen, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Einfügen eines Feldes mit Text darin

 Sobald wir ein Dokument haben, können wir ein Feld mit Text darin einfügen, indem wir`DocumentBuilder` Objekt. Um beispielsweise ein "INCLUDETEXT"-Feld mit dem Text "Text im Feld" einzufügen, können wir das`InsertField` Methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Schritt 3: Verwenden der Funktion „Text in Feldern ignorieren“

 Um Text in Feldern bei nachfolgenden Operationen zu ignorieren, können wir einen`FindReplaceOptions` Objekt und setzen Sie den`IgnoreFields`Eigentum an`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Schritt 4: Verwenden regulärer Ausdrücke für Suchen und Ersetzen

Um Such- und Ersetzungsvorgänge im Text des Dokuments durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens "e" und ersetzen sie durch ein Sternchen "* ". Wir verwenden .NETs`Regex` Klasse dafür:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Schritt 5: Anzeigen der geänderten Dokumentausgabe

 Nach der Anwendung von Suchen und Ersetzen können wir den geänderten Inhalt des Dokuments anzeigen, indem wir`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Schritt 6: Optionen zum Einschließen von Feldern ändern

 Wir schließen den Text in den Feldern in das Ausgabeergebnis ein, wir können die Optionen ändern, um die Felder nicht zu ignorieren. Dazu setzen wir die`IgnoreFields`Eigentum an`false`:

```csharp
options.IgnoreFields = false;
```

## Schritt 7: Anzeige des geänderten Dokuments mit den Feldern

Nachdem wir die Optionen geändert haben, können wir die Suche und den Ersetzungsvorgang erneut durchführen, um das Ergebnis mit dem Text innerhalb der eingeschlossenen Felder zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Beispielquellcode zum Ignorieren von Text in Feldern mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Verwendung der Funktion „Text in Feldern ignorieren“ mit Aspose.Words für .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Feld mit Text einfügen.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in Feldern ignorieren“ in Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um ein Dokument zu erstellen, ein Feld mit Text einzufügen, die Funktion „Text in Feldern ignorieren“ zu verwenden, Such- und Ersetzungsvorgänge mit regulären Ausdrücken durchzuführen und das geänderte Dokument anzuzeigen.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Text in Feldern ignorieren“ in Aspose.Words für .NET?

A: Mit der Funktion „Text in Feldern ignorieren“ in Aspose.Words für .NET können Sie angeben, ob der Text in Feldern bei bestimmten Vorgängen, wie z. B. beim Suchen und Ersetzen von Text, ignoriert werden soll. Wenn diese Funktion aktiviert ist, wird der Text in den Feldern bei Vorgängen nicht berücksichtigt.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie eine`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie kann ich mit Aspose.Words für .NET ein Feld mit Text in ein Dokument einfügen?

 A: Sobald Sie ein Dokument haben, können Sie ein Feld mit Text darin einfügen, indem Sie`DocumentBuilder` Objekt. Um beispielsweise ein "INCLUDETEXT"-Feld mit dem Text "Text im Feld" einzufügen, können Sie das`InsertField` Methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### F: Wie kann ich Text in Feldern in Aspose.Words für .NET ignorieren?

 A: Um Text in Feldern bei nachfolgenden Operationen zu ignorieren, können Sie einen`FindReplaceOptions` Objekt und setzen Sie den`IgnoreFields`Eigentum an`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### F: Wie kann ich in Aspose.Words für .NET mit regulären Ausdrücken suchen und ersetzen?

 A: Um Such- und Ersetzungsoperationen im Text des Dokuments mithilfe regulärer Ausdrücke durchzuführen, können Sie die .NET`Regex` Klasse. Um beispielsweise nach allen Vorkommen des Buchstabens "e" zu suchen und diese durch ein Sternchen zu ersetzen "* " können Sie eine`Regex` Objekt und verwenden Sie es mit dem`Replace` Methode:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### F: Wie kann ich die geänderte Ausgabe des Dokuments in Aspose.Words für .NET anzeigen?

 A: Nach dem Anwenden von Such- und Ersetzungsvorgängen können Sie den geänderten Inhalt des Dokuments mithilfe der`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

#### F: Wie kann ich die Felder in das Ausgabeergebnis in Aspose.Words für .NET einschließen?

 A: Um den Text in den Feldern in das Ausgabeergebnis einzuschließen, können Sie die Optionen so ändern, dass die Felder nicht ignoriert werden. Dazu können Sie die`IgnoreFields` Eigentum der`FindReplaceOptions` Einwände erheben gegen`false`:

```csharp
options.IgnoreFields = false;
```

#### F: Wie kann ich das geänderte Dokument mit den Feldern in Aspose.Words für .NET anzeigen?

A: Nachdem Sie die Optionen zum Einschließen von Feldern geändert haben, können Sie die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem Text innerhalb der eingeschlossenen Felder zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```