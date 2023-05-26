---
title: Ignorieren Sie den Text innerhalb der Löschrevisionen
linktitle: Ignorieren Sie den Text innerhalb der Löschrevisionen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Funktion „Text in Löschrevisionen ignorieren“ von Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Text in Löschrevisionen ignorieren“ in der Aspose.Words für .NET-Bibliothek verwendet wird. Diese Funktion ist nützlich, wenn wir beim Arbeiten mit Dokumenten Text in Löschrevisionen ignorieren möchten.

## Übersicht über die Aspose.Words für .NET-Bibliothek

Bevor ich auf die Codedetails eingehe, möchte ich kurz die Bibliothek Aspose.Words für .NET vorstellen. Es handelt sich um eine leistungsstarke Bibliothek, die das Erstellen, Ändern und Konvertieren von Word-Dokumenten in .NET-Anwendungen ermöglicht. Es bietet viele erweiterte Funktionen für die Arbeit mit Dokumenten, einschließlich Revisionsverwaltung.

## Verstehen der Funktion „Text in Löschrevisionen ignorieren“.

Mit der Funktion „Text in Löschrevisionen ignorieren“ in Aspose.Words für .NET können Sie festlegen, ob Text in Löschrevisionen bei bestimmten Vorgängen, z. B. beim Suchen und Ersetzen von Text, ignoriert werden soll. Wenn diese Funktion aktiviert ist, wird gelöschter Text in Revisionen bei Vorgängen nicht berücksichtigt.

## Schritt 1: Erstellen eines neuen Dokuments mit Aspose.Words für .NET

 Bevor wir mit der Bearbeitung von Text in einem Dokument beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Einfügen von nicht überarbeitetem Text in das Dokument

 Sobald wir ein Dokument haben, können wir mit a ungeprüften Text einfügen`DocumentBuilder` Objekt. Um beispielsweise den Text „Gelöschter Text“ einzufügen, können wir den verwenden`Writeln` Und`Write` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Schritt 3: Entfernen eines Absatzes mit Nachverfolgung von Revisionen

Um die Verwendung der Funktion „Text in Revisionen ignorieren“ zu veranschaulichen, löschen wir mithilfe der Revisionsverfolgung einen Absatz aus dem Dokument. Dadurch können wir sehen, wie sich diese Funktion auf nachfolgende Vorgänge auswirkt.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Schritt 4: Anwenden der Funktion „Text in Löschrevisionen ignorieren“.

 Nachdem wir nun unser Dokument durch das Löschen eines Absatzes vorbereitet haben, können wir die Funktion „Text in Revisionen ignorieren“ mit a aktivieren`FindReplaceOptions` Objekt. Wir werden das einstellen`IgnoreDeleted` Eigentum zu`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Schritt 5: Verwenden regulärer Ausdrücke zum Suchen und Ersetzen

Um Such- und Ersetzungsvorgänge für den Text des Dokuments durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens „e“ und ersetzen sie durch ein Sternchen „* ". .NETZ`Regex` Hierfür wird die Klasse verwendet:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Schritt 6: Anzeige der geänderten Dokumentausgabe

Nachdem wir das Suchen und Ersetzen angewendet haben, können wir den geänderten Inhalt des Dokuments mithilfe von anzeigen`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Schritt 7: Ändern der Optionen, um gelöschten Text einzuschließen

 Wenn wir gelöschten Text in das Ausgabeergebnis einbeziehen möchten, können wir die Optionen so ändern, dass gelöschter Text nicht ignoriert wird. Hierzu legen wir die fest`IgnoreDeleted` Eigentum zu`false`:

```csharp
options. IgnoreDeleted = false;
```

## Schritt 8: Ausgabe des geänderten Dokuments mit gelöschtem Text

Nachdem wir die Optionen geändert haben, können wir die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem gelöschten Text zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Beispielquellcode für „Text in Revisionen ignorieren“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Funktion „Text in Revisionen ignorieren“ mit Aspose.Words für .NET zu demonstrieren:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Fügen Sie nicht überarbeiteten Text ein.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Entfernen Sie den ersten Absatz mit der Nachverfolgung von Revisionen.
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

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in Löschrevisionen ignorieren“ in Aspose.Words für .NET verwendet wird. Diese Funktion ist nützlich, um beim Bearbeiten von Dokumenten Text in Löschrevisionen zu ignorieren. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein Dokument zu erstellen, Text einzufügen, einen Absatz mit Revisionsverfolgung zu löschen, die Funktion „Text in Revisionen ignorieren“ anzuwenden und Such- und Ersetzungsvorgänge durchzuführen.

