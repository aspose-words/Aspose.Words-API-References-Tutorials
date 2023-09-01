---
title: Erkennen Sie intelligente Kunstformen
linktitle: Erkennen Sie intelligente Kunstformen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Smart Art-Formen in einem Word-Dokument erkennen und grafische Darstellungen identifizieren.
type: docs
weight: 10
url: /de/net/programming-with-shapes/detect-smart-art-shape/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET Smart Art-Formen in einem Word-Dokument erkennen. Smart-Art-Formen sind grafische Darstellungen, mit denen Informationen und Ideen visuell dargestellt werden.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Schritt 3: Erkennen Sie intelligente Kunstformen
 Durchlaufen Sie die untergeordneten Knoten des Typs`Shape` im Dokument mit dem`GetChildNodes`Methode. Überprüfen Sie mithilfe von, ob jede Form über Smart Art verfügt`HasSmart Art` Eigentum.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Schritt 4: Ergebnis ausgeben
Drucken Sie die Anzahl der im Dokument erkannten Formen mit Smart Art aus.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Beispielquellcode für „Smart Art Shape erkennen“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich Smart Art-Formen in Ihrem Word-Dokument erkannt.