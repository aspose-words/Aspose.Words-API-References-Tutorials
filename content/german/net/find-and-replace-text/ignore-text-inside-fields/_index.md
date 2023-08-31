---
title: Text in Feldern ignorieren
linktitle: Text in Feldern ignorieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Text in Feldern ignorieren“ von Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/find-and-replace-text/ignore-text-inside-fields/
---
In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Text in Feldern ignorieren“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Diese Funktion ist nützlich, wenn wir beim Bearbeiten von Dokumenten den Text in den Feldern ignorieren möchten.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Bearbeitung von Text in Feldern beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Einfügen eines Feldes mit Text darin

 Sobald wir ein Dokument haben, können wir mit a ein Feld mit Text darin einfügen`DocumentBuilder` Objekt. Um beispielsweise ein „INCLUDETEXT“-Feld mit dem Text „Text im Feld“ einzufügen, können wir das verwenden`InsertField` Methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Schritt 3: Verwenden der Funktion „Text in Feldern ignorieren“.

 Um Text in Feldern bei nachfolgenden Vorgängen zu ignorieren, können wir a verwenden`FindReplaceOptions` Objekt und legen Sie das fest`IgnoreFields` Eigentum zu`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Schritt 4: Verwenden regulärer Ausdrücke zum Suchen und Ersetzen

Um Such- und Ersetzungsvorgänge für den Text des Dokuments durchzuführen, verwenden wir reguläre Ausdrücke. In unserem Beispiel suchen wir nach allen Vorkommen des Buchstabens „e“ und ersetzen sie durch ein Sternchen „* ". Wir werden .NETs verwenden`Regex` Klasse dafür:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Schritt 5: Anzeigen der geänderten Dokumentausgabe

Nachdem wir das Suchen und Ersetzen angewendet haben, können wir den geänderten Inhalt des Dokuments mithilfe von anzeigen`GetText` Methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Schritt 6: Optionen ändern, um Felder einzubeziehen

Wenn wir den Text in den Feldern in das Ausgabeergebnis einbeziehen, können wir die Optionen so ändern, dass die Felder nicht ignoriert werden. Hierzu legen wir die fest`IgnoreFields` Eigentum zu`false`:

```csharp
options.IgnoreFields = false;
```

## Schritt 7: Anzeige des geänderten Dokuments mit den Feldern

Nachdem wir die Optionen geändert haben, können wir die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem Text in den enthaltenen Feldern zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Beispielquellcode für „Text in Feldern ignorieren“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung der Funktion „Text in Feldern ignorieren“ mit Aspose.Words für .NET zu demonstrieren:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Feld mit Text darin einfügen.
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

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Text in Feldern ignorieren“ in Aspose.Words für .NET verwendet wird. Wir haben eine Schritt-für-Schritt-Anleitung befolgt, um ein Dokument zu erstellen, ein Feld mit Text darin einzufügen, die Funktion „Text in Feldern ignorieren“ zu verwenden, Such- und Ersetzungsvorgänge mit regulären Ausdrücken durchzuführen und das geänderte Dokument anzuzeigen.

### FAQs

#### F: Was ist die Funktion „Text in Feldern ignorieren“ in Aspose.Words für .NET?

A: Mit der Funktion „Text in Feldern ignorieren“ in Aspose.Words für .NET können Sie festlegen, ob der Text in Feldern bei bestimmten Vorgängen ignoriert werden soll, z. B. beim Suchen und Ersetzen von Text. Wenn diese Funktion aktiviert ist, wird der Text in den Feldern bei Vorgängen nicht berücksichtigt.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie ein instanziieren`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie kann ich mit Aspose.Words für .NET ein Feld mit Text in ein Dokument einfügen?

 A: Sobald Sie ein Dokument haben, können Sie mithilfe von ein Feld mit darin enthaltenem Text einfügen`DocumentBuilder` Objekt. Um beispielsweise ein „INCLUDETEXT“-Feld mit dem Text „Text im Feld“ einzufügen, können Sie die verwenden`InsertField` Methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### F: Wie kann ich Text in Feldern in Aspose.Words für .NET ignorieren?

A: Um Text in Feldern bei nachfolgenden Vorgängen zu ignorieren, können Sie a verwenden`FindReplaceOptions` Objekt und legen Sie das fest`IgnoreFields` Eigentum zu`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### F: Wie kann ich die Felder in das Ausgabeergebnis in Aspose.Words für .NET einbeziehen?

 A: Um den Text in den Feldern in das Ausgabeergebnis einzubeziehen, können Sie die Optionen so ändern, dass die Felder nicht ignoriert werden. Hierfür können Sie die einstellen`IgnoreFields` Eigentum der`FindReplaceOptions` widersprechen`false`:

```csharp
options.IgnoreFields = false;
```

#### F: Wie kann ich das geänderte Dokument mit den Feldern in Aspose.Words für .NET anzeigen?

A: Nachdem Sie die Optionen so geändert haben, dass sie Felder einbeziehen, können Sie die Suche und das Ersetzen erneut durchführen, um das Ergebnis mit dem Text in den enthaltenen Feldern zu erhalten:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```