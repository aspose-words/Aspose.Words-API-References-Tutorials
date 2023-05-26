---
title: Zum Absatz wechseln
linktitle: Zum Absatz wechseln
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Funktion „In Absatz verschieben“ von Aspose.Words für .NET verwenden, um programmgesteuert in Absätzen in Word-Dokumenten zu navigieren und diese zu bearbeiten.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-paragraph/
---

In diesem Schritt-für-Schritt-Beispiel erkunden wir die Funktion „In Absatz verschieben“ von Aspose.Words für .NET. Mit dieser Funktion können Entwickler programmgesteuert durch Absätze in einem Word-Dokument navigieren und diese bearbeiten. Wenn Sie dieser Anleitung folgen, erfahren Sie, wie Sie die Funktion „In Absatz verschieben“ effektiv implementieren und nutzen.

Der obige Code demonstriert die Verwendung der Funktion „In Absatz verschieben“. Lassen Sie uns jeden Schritt im Detail verstehen:

## Schritt 1: Laden des Dokuments

 Wir beginnen mit dem Laden des Word-Dokuments in eine Instanz von`Document` Klasse. Der`MyDir`Die Variable stellt den Verzeichnispfad dar, in dem sich das Dokument befindet. Sie sollten es durch den tatsächlichen Verzeichnispfad ersetzen oder den Code entsprechend ändern.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## Schritt 2: Initialisieren des DocumentBuilder

 Als nächstes erstellen wir eine`DocumentBuilder` Objekt und verknüpfen es mit dem geladenen Dokument. Der`DocumentBuilder` Die Klasse stellt verschiedene Methoden und Eigenschaften zur Bearbeitung des Dokumentinhalts bereit.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Zu einem bestimmten Absatz wechseln

 Der`MoveToParagraph` Die Methode wird verwendet, um den Dokumentgenerator an einem bestimmten Absatz im Dokument zu positionieren. Es benötigt zwei Parameter: den Index des Zielabsatzes und die Zeichenposition innerhalb dieses Absatzes (0 steht für den Anfang des Absatzes).

Im bereitgestellten Beispiel bewegen wir uns zum dritten Absatz (Index 2) des Dokuments:

```csharp
builder.MoveToParagraph(2, 0);
```

## Schritt 4: Ändern des Absatzinhalts

 Sobald der Builder am gewünschten Absatz positioniert ist, können wir den verwenden`Writeln`Methode zum Hinzufügen oder Ändern des Inhalts dieses Absatzes. In diesem Fall fügen wir den Text „Dies ist der 3. Absatz“ hinzu.

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### Beispielquellcode für „In Absatz verschieben“ mit Aspose.Words für .NET

Nachfolgend finden Sie den vollständigen Beispielquellcode für die Implementierung der Funktion „In Absatz verschieben“ mit Aspose.Words für .NET:

```csharp

	Document doc = new Document(MyDir + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToParagraph(2, 0);
	builder.Writeln("This is the 3rd paragraph.");
	
```

Wenn Sie dieser Anleitung folgen und die Funktion „In Absatz verschieben“ verwenden, können Sie Absätze in Word-Dokumenten mit Aspose.Words für .NET programmgesteuert bearbeiten.

