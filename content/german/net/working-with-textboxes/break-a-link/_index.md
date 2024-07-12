---
title: Weiterleitungslink im Word-Dokument unterbrechen
linktitle: Weiterleitungslink im Word-Dokument unterbrechen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Vorwärtslinks in einem Word-Dokument unterbrechen.
type: docs
weight: 10
url: /de/net/working-with-textboxes/break-a-link/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek, die verschiedene Funktionen für die programmgesteuerte Textverarbeitung mit Microsoft Word-Dokumenten bietet. Eine der nützlichen Funktionen ist die Möglichkeit, Vorwärtslinks in einem Word-Dokument zu unterbrechen. In diesem Tutorial untersuchen wir Quellcode in C#, der zeigt, wie man mit Aspose.Words für .NET Vorwärtslinks in einem Word-Dokument unterbricht.

## Schritt 1: Vorschau des C#-Quellcodes

Der bereitgestellte C#-Quellcode konzentriert sich auf die Funktion „Break A Link“ von Aspose.Words für .NET. Er zeigt, wie ein Link in einer TextBox-Form innerhalb eines Dokuments unterbrochen wird. Der Code stellt verschiedene Szenarien zum Unterbrechen von Links vor und bietet klare Anweisungen, wie die gewünschten Ergebnisse erzielt werden können.

## Schritt 2: Einrichten des Dokuments und Erstellen einer TextBox-Form

 Zunächst müssen wir das Dokument einrichten und eine TextBox-Form erstellen. Der folgende Code initialisiert eine neue Instanz der`Document` Klasse und erstellt eine Textfeldform:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Schritt 3: Weiterleitungslink im Textfeld unterbrechen

 Um einen Vorwärtslink in der TextBox zu unterbrechen, können wir den`BreakForwardLink()` -Methode. Diese Methode unterbricht den Link zur nächsten Form in der Sequenz. Der folgende Code zeigt, wie ein Vorwärtslink unterbrochen wird:

```csharp
textBox.BreakForwardLink();
```

## Schritt 4: Unterbrechen Sie einen Weiterleitungslink, indem Sie einen Nullwert festlegen

 Alternativ können wir einen Weiterleitungslink unterbrechen, indem wir die TextBox`Next`Eigentum an`null`. Dadurch wird die Verbindung zur nächsten Form effektiv entfernt. Der folgende Code demonstriert diesen Ansatz:

```csharp
textBox. Next = null;
```

## Schritt 5: Einen Link trennen, der zur TextBox führt

 In manchen Fällen müssen wir einen Link unterbrechen, der zur TextBox-Form führt. Dies erreichen wir durch den Aufruf des`BreakForwardLink()` Methode auf der`Previous` Formular, das die Verknüpfung zur TextBox unterbricht. Hier ist ein Beispiel, wie man eine solche Verknüpfung unterbricht:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Beispielquellcode zum Aufheben einer Verknüpfung mit Aspose.Words für .NET

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

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie Umleitungslinks in einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET unterbrechen. Indem Sie die Schritte in dieser Anleitung befolgt haben, konnten Sie das Dokument einrichten, eine TextBox-Form erstellen und die Umleitungslinks mithilfe verschiedener Methoden unterbrechen.

### FAQs zum Weiterleitungslink im Word-Dokument

#### F: Welche Bibliothek wird verwendet, um Umleitungslinks in einem Word-Dokument mit Aspose.Words für .NET zu unterbrechen?

A: Um Umleitungslinks in einem Word-Dokument mit Aspose.Words für .NET zu unterbrechen, wird die Bibliothek Aspose.Words für .NET verwendet.

#### F: Wie unterbricht man einen Umleitungslink in einem Textfeld?

 A: Um einen Weiterleitungslink in einer TextBox zu unterbrechen, können Sie den`BreakForwardLink()` -Methode. Diese Methode unterbricht die Verknüpfung zur nächsten Form in der Sequenz.

#### F: Wie kann ich einen Umleitungslink durch Festlegen eines Nullwerts unterbrechen?

A: Alternativ können Sie einen Weiterleitungslink unterbrechen, indem Sie den`Next` Eigenschaft der TextBox auf`null`. Dadurch wird die Verbindung zur nächsten Form effektiv entfernt.

#### F: Wie unterbreche ich einen Link, der zu einer Textbox führt?

 A: In manchen Fällen muss ein Link, der zur TextBox führt, unterbrochen werden. Dies erreichen Sie durch den Aufruf des`BreakForwardLink()` Methode auf der`Previous` Formular, das die Verknüpfung mit der TextBox unterbricht.

#### F: Können wir Umleitungslinks bei anderen Elementen als Textfeldern unterbrechen?

A: Ja, mit Aspose.Words für .NET ist es möglich, Umleitungslinks bei verschiedenen Elementen wie Absätzen, Tabellen, Bildern usw. aufzuheben. Der Vorgang kann je nach dem spezifischen Element, bei dem Sie den Link aufheben möchten, unterschiedlich sein.