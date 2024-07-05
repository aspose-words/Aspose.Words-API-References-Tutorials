---
title: Text in gelöschten Revisionen ignorieren
linktitle: Text in gelöschten Revisionen ignorieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Text in gelöschten Revisionen ignorieren“ von Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Text in Löschrevisionen ignorieren“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Diese Funktion ist nützlich, wenn wir bei der Textverarbeitung mit Dokumenten Text in Löschrevisionen ignorieren möchten.

## Übersicht über die Aspose.Words-Bibliothek für .NET

Bevor ich in die Codedetails eintauche, möchte ich kurz die Aspose.Words-Bibliothek für .NET vorstellen. Es handelt sich um eine leistungsstarke Bibliothek, mit der Word-Dokumente in .NET-Anwendungen erstellt, geändert und konvertiert werden können. Sie bietet viele erweiterte Funktionen für die Textverarbeitung mit Dokumenten, einschließlich Revisionsverwaltung.

## Erläuterung der Funktion „Text in gelöschten Revisionen ignorieren“

Mit der Funktion „Text in gelöschten Revisionen ignorieren“ in Aspose.Words für .NET können Sie angeben, ob Text in gelöschten Revisionen bei bestimmten Vorgängen, z. B. beim Suchen und Ersetzen von Text, ignoriert werden soll. Wenn diese Funktion aktiviert ist, wird gelöschter Text in Revisionen bei Vorgängen nicht berücksichtigt.

## Schritt 1: Erstellen eines neuen Dokuments mit Aspose.Words für .NET

 Bevor wir mit der Textbearbeitung in einem Dokument beginnen, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Nicht überarbeiteten Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir ungeprüften Text einfügen mit einem`DocumentBuilder` Objekt. Um beispielsweise den Text "Gelöschter Text" einzufügen, können wir das`Writeln` Und`Write` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Schritt 3: Entfernen eines Absatzes mit Revisionsverfolgung

Um die Verwendung der Funktion „Text in gelöschten Revisionen ignorieren“ zu veranschaulichen, löschen wir mithilfe der Revisionsverfolgung einen Absatz aus dem Dokument. So können wir sehen, wie sich diese Funktion auf nachfolgende Vorgänge auswirkt.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Schritt 4: Anwenden der Funktion „Text in gelöschten Revisionen ignorieren“

 Nachdem wir nun unser Dokument durch das Löschen eines Absatzes vorbereitet haben, können wir die Funktion "Text in gelöschten Revisionen ignorieren" aktivieren, indem wir`FindReplaceOptions` Objekt. Wir setzen den`IgnoreDeleted`Eigentum an`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Schritt 5: Verwenden regulärer Ausdrücke für Suchen und Ersetzen

Um Such- und Ersetzungsvorgänge im Text des Dokuments durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens "e" und ersetzen sie durch ein Sternchen "* ". .NETZ`Regex` Hierzu wird die Klasse verwendet:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Schritt 6: Anzeige der geänderten Dokumentausgabe

 Nach der Anwendung von Suchen und Ersetzen können wir den geänderten Inhalt des Dokuments anzeigen, indem wir`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Schritt 7: Ändern der Optionen zum Einschließen gelöschten Textes

 Wenn wir gelöschten Text in das Ausgabeergebnis einschließen möchten, können wir die Optionen ändern, um gelöschten Text nicht zu ignorieren. Dazu setzen wir die`IgnoreDeleted`Eigentum an`false`:

```csharp
options. IgnoreDeleted = false;
```

## Schritt 8: Ausgabe des geänderten Dokuments mit gelöschtem Text

Nachdem wir die Optionen geändert haben, können wir die Suche und Ersetzung erneut durchführen, um das Ergebnis mit dem gelöschten Text zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Beispielquellcode zum Ignorieren von Text in gelöschten Revisionen mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration der Verwendung der Funktion „Text in gelöschten Revisionen ignorieren“ mit Aspose.Words für .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Nicht überarbeiteten Text einfügen.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Entfernen Sie den ersten Absatz mit der Revisionsverfolgung.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in gelöschten Revisionen ignorieren“ in Aspose.Words für .NET verwendet wird. Diese Funktion ist nützlich, um Text in gelöschten Revisionen beim Bearbeiten von Dokumenten zu ignorieren. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein Dokument zu erstellen, Text einzufügen, einen Absatz mit Revisionsverfolgung zu löschen, die Funktion „Text in gelöschten Revisionen ignorieren“ anzuwenden und Such- und Ersetzungsvorgänge durchzuführen.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Text in gelöschten Revisionen ignorieren“ in Aspose.Words für .NET?

A: Mit der Funktion „Text in gelöschten Revisionen ignorieren“ in Aspose.Words für .NET können Sie angeben, ob Text in gelöschten Revisionen bei bestimmten Vorgängen, wie z. B. beim Suchen und Ersetzen von Text, ignoriert werden soll. Wenn diese Funktion aktiviert ist, wird gelöschter Text in Revisionen bei Vorgängen nicht berücksichtigt.

#### F: Was ist Aspose.Words für .NET?

A: Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Konvertieren von Word-Dokumenten in .NET-Anwendungen. Sie bietet viele erweiterte Funktionen für die Textverarbeitung mit Dokumenten, einschließlich Revisionsverwaltung.

#### F: Wie erstelle ich in Aspose.Words für .NET ein neues Dokument?

 A: Bevor Sie mit der Textbearbeitung in einem Dokument beginnen, müssen Sie ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt. Hier ist ein Beispielcode zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie füge ich mit Aspose.Words für .NET unbearbeiteten Text in ein Dokument ein?

 A: Sobald Sie ein Dokument haben, können Sie ungeprüften Text einfügen mit einem`DocumentBuilder` Objekt. Um beispielsweise den Text "Gelöschter Text" einzufügen, können Sie das`Writeln` Und`Write` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### F: Wie lösche ich einen Absatz mit Revisionsverfolgung in Aspose.Words für .NET?

A: Um die Verwendung der Funktion „Text in gelöschten Revisionen ignorieren“ zu veranschaulichen, löschen wir mithilfe der Revisionsverfolgung einen Absatz aus dem Dokument. Dadurch können wir sehen, wie sich diese Funktion auf nachfolgende Vorgänge auswirkt.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### F: Wie aktiviere ich die Funktion „Text in gelöschten Revisionen ignorieren“ in Aspose.Words für .NET?

 A: Nachdem wir nun unser Dokument durch das Löschen eines Absatzes vorbereitet haben, können wir die Funktion „Text in gelöschten Revisionen ignorieren“ aktivieren, indem wir`FindReplaceOptions` Objekt. Wir setzen den`IgnoreDeleted`Eigentum an`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### F: Wie kann ich in Aspose.Words für .NET mit regulären Ausdrücken suchen und ersetzen?

A: Um Such- und Ersetzungsvorgänge im Text des Dokuments durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens "e" und ersetzen sie durch ein Sternchen "* ". Wir werden die .NET`Regex` Klasse dafür:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### F: Wie kann ich geänderte Dokumentinhalte in Aspose.Words für .NET anzeigen?

A: Nach der Anwendung von Suchen und Ersetzen können wir den geänderten Inhalt des Dokuments anzeigen, indem wir`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

#### F: Wie schließe ich gelöschten Text in das Ausgabeergebnis in Aspose.Words für .NET ein?

 A: Wenn wir gelöschten Text in das Ausgabeergebnis einschließen möchten, können wir die Optionen ändern, um gelöschten Text nicht zu ignorieren. Dazu setzen wir die`IgnoreDeleted`Eigentum an`false`:

```csharp
options. IgnoreDeleted = false;
```

#### F: Wie zeige ich in Aspose.Words für .NET bearbeitete Dokumente mit gelöschtem Text an?

A: Nachdem wir die Optionen geändert haben, können wir eine neue Suche und Ersetzung durchführen, um das Ergebnis mit dem gelöschten Text zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
