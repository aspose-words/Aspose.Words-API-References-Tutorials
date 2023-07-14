---
title: Zum Anfangs-Ende des Dokuments verschieben
linktitle: Zum Anfangs-Ende des Dokuments verschieben
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