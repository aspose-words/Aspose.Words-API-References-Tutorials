---
title: Text in eingefügten Revisionen ignorieren
linktitle: Text in eingefügten Revisionen ignorieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Text in Einfügerevisionen ignorieren“ von Aspose.Words für .NET verwenden, um Einfügerevisionen in Word-Dokumenten zu bearbeiten.
type: docs
weight: 10
url: /de/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie man die Funktion „Text in Insert-Revisionen ignorieren“ in der Aspose.Words-Bibliothek für .NET verwendet. Diese Funktion ist nützlich, wenn wir beim Bearbeiten von Dokumenten Text in Insert-Revisionen ignorieren möchten.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

 Bevor wir mit der Textbearbeitung in Insert-Revisionen beginnen, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Text mit Revisionsverfolgung einfügen

 Sobald wir ein Dokument haben, können wir Text mit Revisionsverfolgung einfügen, indem wir`DocumentBuilder`Objekt. Um beispielsweise den Text "Eingefügt" mit Revisionsverfolgung einzufügen, können wir das`StartTrackRevisions`, `Writeln` Und`StopTrackRevisions` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Schritt 3: Nicht überprüften Text einfügen

 Neben Text mit Revisionsverfolgung können wir auch nicht überarbeiteten Text einfügen, indem wir`DocumentBuilder` Objekt. Um beispielsweise den Text "Text" ohne Überarbeitung einzufügen, können wir das`Write` Methode:

```csharp
builder.Write("Text");
```

## Schritt 4: Verwenden der Funktion „Text in eingefügten Revisionen ignorieren“

 Um Text in Einfügerevisionen bei nachfolgenden Operationen zu ignorieren, können wir einen`FindReplaceOptions` Objekt und setzen Sie den`IgnoreInserted`Eigentum an`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Schritt 5: Verwenden regulärer Ausdrücke für Suchen und Ersetzen

Um Suchvorgänge und Ersetzungen im Dokumenttext durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens "e" und ersetzen sie durch ein Asterisk "* ". Wir verwenden .NETs`Regex` Klasse dafür:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Schritt 6: Anzeigen der geänderten Dokumentausgabe

 Nach der Anwendung von Suchen und Ersetzen können wir den geänderten Inhalt des Dokuments anzeigen, indem wir`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Schritt 7: Ändern der Optionen zum Einschließen von Einfügerevisionen

Wenn wir den Text innerhalb der Insert-Revisionen in das Ausgabeergebnis einbeziehen möchten, können wir die Optionen so ändern, dass die Insert-Revisionen nicht ignoriert werden. Dazu setzen wir die`IgnoreInserted`Eigentum an`false`:

```csharp
options.IgnoreInserted = false;
```

## Schritt 8: Anzeigen des geänderten Dokuments mit eingefügten Revisionen

Nachdem wir die Optionen geändert haben, können wir die Suche und den Ersetzungsvorgang erneut durchführen, um das Ergebnis mit dem Text innerhalb der eingefügten Revisionen zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Beispielquellcode zum Ignorieren von Text in Einfügerevisionen mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Verwendung der Funktion „Text innerhalb von Insert Revisions ignorieren“ mit Aspose.Words für .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Fügen Sie Text mit Revisionsverfolgung ein.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Nicht überarbeiteten Text einfügen.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in eingefügten Revisionen ignorieren“ in Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung zum Erstellen eines Dokuments befolgt, Text mit nachverfolgten Revisionen und nicht überarbeitetem Text eingefügt, die Funktion „Text in eingefügten Revisionen ignorieren“ verwendet, Such- und Ersetzungsvorgänge mit regulären Ausdrücken ausgeführt und das geänderte Dokument angezeigt.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Text in eingefügten Revisionen ignorieren“ in Aspose.Words für .NET?

A: Mit der Funktion „Text in Einfügerevisionen ignorieren“ in Aspose.Words für .NET können Sie angeben, ob der Text in Einfügerevisionen bei bestimmten Vorgängen, wie z. B. Suchen und Ersetzen von Text, ignoriert werden soll. Wenn diese Funktion aktiviert ist, wird der Text in den Einfügerevisionen bei Vorgängen nicht berücksichtigt.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie eine`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie kann ich in Aspose.Words für .NET Text mit Revisionsverfolgung einfügen?

A: Sobald Sie ein Dokument haben, können Sie Text mit Revisionsverfolgung einfügen, indem Sie`DocumentBuilder` Objekt. Um beispielsweise den Text "Eingefügt" mit Revisionsverfolgung einzufügen, können Sie das`StartTrackRevisions`, `Writeln` , Und`StopTrackRevisions` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### F: Wie kann ich unveränderten Text in Aspose.Words für .NET einfügen?

 A: Neben Text mit Revisionsverfolgung können Sie auch nicht überarbeiteten Text einfügen, indem Sie`DocumentBuilder` Objekt. Um beispielsweise den Text "Text" ohne Überarbeitung einzufügen, können Sie das`Write` Methode:

```csharp
builder.Write("Text");
```

#### F: Wie kann ich Text beim Einfügen von Revisionen in Aspose.Words für .NET ignorieren?

 A: Um Text in Einfügerevisionen bei nachfolgenden Operationen zu ignorieren, können Sie einen`FindReplaceOptions` Objekt und setzen Sie den`IgnoreInserted`Eigentum an`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
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

#### F: Wie kann ich die Einfügerevisionen in das Ausgabeergebnis in Aspose.Words für .NET einschließen?

 A: Um den Text innerhalb der Insert-Revisionen in das Ausgabeergebnis einzuschließen, können Sie die Optionen so ändern, dass die Insert-Revisionen nicht ignoriert werden. Dazu können Sie die`IgnoreInserted` Eigentum der`FindReplaceOptions` Einwände erheben gegen`false`:

```csharp
options.IgnoreInserted = false;
```

#### F: Wie kann ich das geänderte Dokument mit den eingefügten Revisionen in Aspose.Words für .NET anzeigen?

A: Nachdem Sie die Optionen so geändert haben, dass Einfügerevisionen einbezogen werden, können Sie die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem Text innerhalb der Einfügerevisionen zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```