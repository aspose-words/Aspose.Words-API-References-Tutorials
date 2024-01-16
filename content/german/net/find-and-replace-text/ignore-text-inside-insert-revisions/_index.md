---
title: Text in Einfügungsrevisionen ignorieren
linktitle: Text in Einfügungsrevisionen ignorieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Text in Einfügungsrevisionen ignorieren“ von Aspose.Words für .NET verwenden, um Einfügungsrevisionen in Word-Dokumenten zu bearbeiten.
type: docs
weight: 10
url: /de/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Text in Revisionen ignorieren“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Diese Funktion ist nützlich, wenn wir beim Bearbeiten von Dokumenten Text in Einfügungsrevisionen ignorieren möchten.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Bearbeitung von Text innerhalb von Einfügerevisionen beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Text mit Revisionsverfolgung einfügen

 Sobald wir ein Dokument haben, können wir mithilfe von a Text mit Revisionsverfolgung einfügen`DocumentBuilder`Objekt. Um beispielsweise den „Eingefügten“ Text mit Revisionsverfolgung einzufügen, können wir die verwenden`StartTrackRevisions`, `Writeln` Und`StopTrackRevisions` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Schritt 3: Fügen Sie nicht überprüften Text ein

 Zusätzlich zu Text mit Revisionsverfolgung können wir mit dem auch unrevidierten Text einfügen`DocumentBuilder` Objekt. Um beispielsweise den Text „Text“ ohne Überarbeitung einzufügen, können wir den verwenden`Write` Methode:

```csharp
builder.Write("Text");
```

## Schritt 4: Verwenden der Funktion „Text in Revisionen einfügen“ ignorieren

 Um Text innerhalb von Einfügungsrevisionen bei nachfolgenden Vorgängen zu ignorieren, können wir a verwenden`FindReplaceOptions` Objekt und legen Sie das fest`IgnoreInserted`Eigentum zu`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Schritt 5: Verwenden regulärer Ausdrücke zum Suchen und Ersetzen

Um Suchvorgänge und Ersetzungen im Dokumenttext durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens „e“ und ersetzen sie durch ein Sternchen „* ". Wir werden .NETs verwenden`Regex` Klasse dafür:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Schritt 6: Anzeigen der geänderten Dokumentausgabe

 Nachdem wir das Suchen und Ersetzen angewendet haben, können wir den geänderten Inhalt des Dokuments mithilfe von anzeigen`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Schritt 7: Optionen ändern, um Einfügungsrevisionen einzubeziehen

Wenn wir den Text in den Einfügungsrevisionen in das Ausgabeergebnis einschließen möchten, können wir die Optionen so ändern, dass die Einfügungsrevisionen nicht ignoriert werden. Hierzu legen wir die fest`IgnoreInserted`Eigentum zu`false`:

```csharp
options.IgnoreInserted = false;
```

## Schritt 8: Anzeigen des geänderten Dokuments mit Einfügen von Revisionen

Nachdem wir die Optionen geändert haben, können wir die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem Text in den Einfügungsrevisionen zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Beispielquellcode für Ignore Text Inside Insert Revisions mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Funktion „Text in Revisionen einfügen“ ignorieren mit Aspose.Words für .NET zu demonstrieren:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Fügen Sie Text mit Tracking-Revisionen ein.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Fügen Sie nicht überarbeiteten Text ein.
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

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in Revisionen ignorieren“ in Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung zum Erstellen eines Dokuments, zum Einfügen von Text mit Verfolgung von Revisionen und nicht überarbeitetem Text, zur Verwendung der Funktion „Text in Revisionen einfügen“ ignorieren, zum Durchführen von Such- und Ersetzungsvorgängen mit regulären Ausdrücken und zum Anzeigen des geänderten Dokuments.

### FAQs

#### F: Was ist die Funktion „Text in Einfügungsrevisionen ignorieren“ in Aspose.Words für .NET?

A: Mit der Funktion „Text in Einfügungsrevisionen ignorieren“ in Aspose.Words für .NET können Sie festlegen, ob der Text in Einfügungsrevisionen bei bestimmten Vorgängen ignoriert werden soll, z. B. beim Suchen und Ersetzen von Text. Wenn diese Funktion aktiviert ist, wird der Text in den Einfügungsrevisionen bei Vorgängen nicht berücksichtigt.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie ein instanziieren`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie kann ich Text mit Revisionsverfolgung in Aspose.Words für .NET einfügen?

A: Sobald Sie ein Dokument haben, können Sie mithilfe von a Text mit Revisionsverfolgung einfügen`DocumentBuilder` Objekt. Um beispielsweise den „Eingefügten“ Text mit Revisionsverfolgung einzufügen, können Sie die verwenden`StartTrackRevisions`, `Writeln` , Und`StopTrackRevisions` Methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### F: Wie kann ich unüberarbeiteten Text in Aspose.Words für .NET einfügen?

 A: Zusätzlich zu Text mit Revisionsverfolgung können Sie mit dem auch unrevidierten Text einfügen`DocumentBuilder` Objekt. Um beispielsweise den Text „Text“ ohne Überarbeitung einzufügen, können Sie die verwenden`Write` Methode:

```csharp
builder.Write("Text");
```

#### F: Wie kann ich Text in Einfügungsrevisionen in Aspose.Words für .NET ignorieren?

 A: Um Text in Einfügungsrevisionen bei nachfolgenden Vorgängen zu ignorieren, können Sie a verwenden`FindReplaceOptions` Objekt und legen Sie das fest`IgnoreInserted`Eigentum zu`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### F: Wie kann ich in Aspose.Words für .NET Suchen und Ersetzen mithilfe regulärer Ausdrücke durchführen?

 A: Um Such- und Ersetzungsvorgänge für den Text des Dokuments mithilfe regulärer Ausdrücke durchzuführen, können Sie .NET verwenden`Regex` Klasse. Um beispielsweise nach allen Vorkommen des Buchstabens „e“ zu suchen und diese durch ein Sternchen zu ersetzen „* ", können Sie eine erstellen`Regex` Objekt und verwenden Sie es mit dem`Replace` Methode:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### F: Wie kann ich die geänderte Ausgabe des Dokuments in Aspose.Words für .NET anzeigen?

 A: Nachdem Sie Such- und Ersetzungsvorgänge angewendet haben, können Sie den geänderten Inhalt des Dokuments mithilfe von anzeigen`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

#### F: Wie kann ich die Einfügungsrevisionen in das Ausgabeergebnis in Aspose.Words für .NET einbeziehen?

 A: Um den Text innerhalb der Einfügungsrevisionen in das Ausgabeergebnis einzubeziehen, können Sie die Optionen so ändern, dass die Einfügungsrevisionen nicht ignoriert werden. Hierfür können Sie die einstellen`IgnoreInserted` Eigentum der`FindReplaceOptions` widersprechen`false`:

```csharp
options.IgnoreInserted = false;
```

#### F: Wie kann ich das geänderte Dokument mit den eingefügten Revisionen in Aspose.Words für .NET anzeigen?

A: Nachdem Sie die Optionen geändert haben, um Einfügungsrevisionen einzubeziehen, können Sie die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem Text innerhalb der Einfügungsrevisionen zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```