---
title: Brechen Sie eine Verbindung
linktitle: Brechen Sie eine Verbindung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Links in einem Word-Dokument unterbrechen.
type: docs
weight: 10
url: /de/net/working-with-textboxes/break-a-link/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek, die verschiedene Funktionen für die programmgesteuerte Arbeit mit Microsoft Word-Dokumenten bietet. Eine seiner nützlichen Funktionen ist die Möglichkeit, Links innerhalb eines Dokuments zu unterbrechen. In diesem Tutorial untersuchen wir Quellcode in C#, der zeigt, wie man einen Link mit Aspose.Words für .NET unterbricht.

## Schritt 1: Vorschau des C#-Quellcodes

Der bereitgestellte C#-Quellcode konzentriert sich auf die Funktion „Break A Link“ von Aspose.Words für .NET. Es zeigt, wie man einen Link in einer TextBox-Form innerhalb eines Dokuments unterbricht. Der Code stellt verschiedene Szenarien zum Unterbrechen von Links vor und bietet klare Anweisungen, wie Sie die gewünschten Ergebnisse erzielen.

## Schritt 2: Einrichten des Dokuments und Erstellen einer TextBox-Form

 Zunächst müssen wir das Dokument einrichten und eine TextBox-Form erstellen. Der folgende Code initialisiert eine neue Instanz von`Document` Klasse und erstellt eine Textfeldform:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Schritt 3: Weiterleitungslink in TextBox unterbrechen

 Um einen Weiterleitungslink in der TextBox zu unterbrechen, können wir die verwenden`BreakForwardLink()`Methode. Diese Methode unterbricht die Verknüpfung zur nächsten Form in der Sequenz. Der folgende Code zeigt, wie man einen Weiterleitungslink unterbricht:

```csharp
textBox.BreakForwardLink();
```

## Schritt 4: Unterbrechen Sie einen Weiterleitungslink, indem Sie einen Nullwert festlegen

 Alternativ können wir einen Weiterleitungslink unterbrechen, indem wir die TextBoxen festlegen`Next` Eigentum zu`null`. Dadurch wird die Verbindung zur nächsten Form effektiv entfernt. Der folgende Code demonstriert diesen Ansatz:

```csharp
textBox. Next = null;
```

## Schritt 5: Unterbrechen Sie einen Link, der zur TextBox führt

 In einigen Fällen müssen wir einen Link unterbrechen, der zur TextBox-Form führt. Wir können dies erreichen, indem wir die aufrufen`BreakForwardLink()` Methode auf der`Previous` Formular, wodurch die Verknüpfung zur TextBox unterbrochen wird. Hier ist ein Beispiel, wie man einen solchen Link unterbricht:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Beispielquellcode zum Unterbrechen einer Verknüpfung mit Aspose.Words für .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Weiterleitungslink unterbrechen.
textBox.BreakForwardLink();

// Unterbrechen Sie einen Weiterleitungslink, indem Sie einen Nullwert festlegen.
textBox. Next = null;

// Unterbrechen Sie einen Link, der zu diesem Textfeld führt.
textBox.Previous?.BreakForwardLink();
```

