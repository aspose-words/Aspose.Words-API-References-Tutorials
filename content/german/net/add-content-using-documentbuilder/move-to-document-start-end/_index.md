---
title: Zum Anfang und Ende des Dokuments im Word-Dokument verschieben
linktitle: Zum Anfang und Ende des Dokuments im Word-Dokument verschieben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET zum Dokumentanfang und -ende in Word-Dokumenten wechseln.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-document-start-end/
---
In diesem Beispiel untersuchen wir die Funktion „An Dokumentanfang/-ende verschieben“ von Aspose.Words für .NET. Aspose.Words ist eine leistungsstarke Bibliothek zur Dokumentbearbeitung, mit der Entwickler Word-Dokumente programmgesteuert erstellen, ändern und konvertieren können. Mit der Funktion „An Anfang/Ende des Dokuments verschieben“ können wir mithilfe der DocumentBuilder-Klasse zum Anfang oder Ende eines Dokuments navigieren.

## Den Quellcode Schritt für Schritt erklären

Lassen Sie uns den Quellcode Schritt für Schritt durchgehen, um zu verstehen, wie Sie die Funktion „An Dokumentanfang/-ende verschieben“ mit Aspose.Words für .NET verwenden.


## Schritt 1: Initialisieren des Dokuments und des Dokument-Builders

Als nächstes initialisieren Sie die Objekte Document und DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Zum Dokumentanfang wechseln

Um die Cursorposition an den Anfang des Dokuments zu verschieben, verwenden Sie die MoveToDocumentStart-Methode der DocumentBuilder-Klasse:

```csharp
builder.MoveToDocumentStart();
```

## Schritt 3: Zum Ende des Dokuments wechseln

Um die Cursorposition an das Ende des Dokuments zu verschieben, verwenden Sie die MoveToDocumentEnd-Methode der DocumentBuilder-Klasse:

```csharp
builder.MoveToDocumentEnd();
```

## Schritt 4: Ausgabe der Cursorposition

Sie können die Cursorposition mit Console.WriteLine oder einer anderen gewünschten Methode ausgeben. Zum Beispiel:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Beispielquellcode für „An Dokumentanfang/-ende verschieben“ mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bewegen Sie die Cursorposition an den Anfang Ihres Dokuments.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Bewegen Sie die Cursorposition an das Ende Ihres Dokuments.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Abschluss

In diesem Beispiel haben wir die Funktion „An Dokumentanfang/-ende verschieben“ von Aspose.Words für .NET untersucht. Wir haben gelernt, wie man mit der DocumentBuilder-Klasse zum Anfang und Ende eines Dokuments navigiert. Diese Funktion ist nützlich, wenn Sie Word-Dokumente programmgesteuert mit Word-Dokumenten verarbeiten und Inhalte an bestimmten Stellen im Dokument bearbeiten oder einfügen müssen.

### FAQs

#### F: Was ist der Zweck der Funktion „An Dokumentanfang/-ende verschieben“ in Aspose.Words für .NET?

A: Mit der Funktion „An Dokumentanfang/-ende verschieben“ in Aspose.Words für .NET können Entwickler mithilfe der DocumentBuilder-Klasse zum Anfang oder Ende eines Word-Dokuments navigieren. Es ist nützlich, um Inhalte an bestimmten Positionen im Dokument programmgesteuert zu bearbeiten oder einzufügen.

#### F: Kann ich diese Funktion mit einem vorhandenen Word-Dokument verwenden?

A: Ja, Sie können die Funktion „An Dokumentanfang/-ende verschieben“ sowohl für neue als auch für vorhandene Word-Dokumente verwenden. Initialisieren Sie einfach den DocumentBuilder mit dem entsprechenden Document-Objekt und verwenden Sie dann die Methoden MoveToDocumentStart und MoveToDocumentEnd, wie im Beispielquellcode gezeigt.

#### F: Wie wirkt sich die Methode DocumentBuilder.MoveToDocumentStart/MoveToDocumentEnd auf den Inhalt des Dokuments aus?

A: Die DocumentBuilder.MoveToDocumentStart-Methode bewegt den Cursor an den Anfang des Dokuments, ohne den vorhandenen Inhalt zu ändern. In ähnlicher Weise bewegt die Methode DocumentBuilder.MoveToDocumentEnd den Cursor an das Ende des Dokuments, ohne den Inhalt zu ändern.

#### F: Kann ich andere Vorgänge ausführen, nachdem ich den Cursor an das Ende des Dokuments bewegt habe?

A: Ja, nachdem Sie den Cursor an das Ende des Dokuments bewegt haben, können Sie den DocumentBuilder weiterhin verwenden, um an dieser Position Inhalte hinzuzufügen oder zu ändern. Die Position des Cursors bleibt am Ende des Dokuments, bis er explizit verschoben wird.

#### F: Wie kann ich die Cursorposition mit Aspose.Words für .NET ausgeben?

A: Sie können die Cursorposition mit Methoden wie Console.WriteLine, Protokollierung oder jedem anderen gewünschten Ausgabemechanismus ausgeben. Im bereitgestellten Beispielquellcode wird Console.WriteLine verwendet, um Meldungen für den Anfang und das Ende des Dokuments anzuzeigen.