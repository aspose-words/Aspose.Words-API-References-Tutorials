---
title: Cursorposition
linktitle: Cursorposition
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET die Cursorposition in einem Word-Dokument abrufen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/cursor-position/
---

In diesem Schritt-für-Schritt-Beispiel erfahren Sie mehr über die Cursorposition in einem Word-Dokument mit Aspose.Words für .NET. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieser Anleitung können Sie den aktuellen Knoten und Absatz abrufen, an dem sich der Cursor im Dokument befindet.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Greifen Sie auf den aktuellen Knoten und Absatz zu
Rufen Sie als Nächstes den aktuellen Knoten und Absatz ab, an dem sich der Cursor befindet. Dies kann mithilfe der Eigenschaften CurrentNode und CurrentParagraph der DocumentBuilder-Klasse erreicht werden:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Schritt 3: Informationen zur Cursorposition abrufen
Jetzt können Sie Informationen über die Cursorposition abrufen. Im folgenden Codeausschnitt drucken wir den Text des aktuellen Absatzes:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Beispielquellcode für die Cursorposition mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Verständnis der Cursorposition mit Aspose.Words für .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET mit der Cursorposition in einem Word-Dokument arbeiten. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie nun den aktuellen Knoten und Absatz abrufen, an dem sich der Cursor im Dokument befindet.

Das Verständnis der Cursorposition ist für verschiedene Szenarios hilfreich, beispielsweise für die Bearbeitung von Dokumentinhalten basierend auf der Cursorposition oder für die Implementierung benutzerdefinierter Bearbeitungsfunktionen.

