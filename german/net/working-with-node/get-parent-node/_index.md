---
title: Übergeordneten Knoten abrufen
linktitle: Übergeordneten Knoten abrufen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den übergeordneten Knoten eines bestimmten Elements abrufen.
type: docs
weight: 10
url: /de/net/working-with-node/get-parent-node/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie Sie mit Aspose.Words für .NET den übergeordneten Knoten abrufen.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Referenzen zur Verwendung von Aspose.Words für .NET in Ihr Projekt importiert haben. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
```

## Schritt 2: Erstellen Sie ein neues Dokument
 In diesem Schritt erstellen wir ein neues Dokument mit`Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 3: Greifen Sie auf den übergeordneten Knoten zu
Um den übergeordneten Knoten eines bestimmten Knotens zu erhalten, müssen wir zuerst auf diesen Knoten zugreifen. In diesem Beispiel greifen wir auf den ersten untergeordneten Knoten des Dokuments zu, bei dem es sich normalerweise um einen Abschnitt handelt.

```csharp
Node section = doc.FirstChild;
```

## Schritt 4: Überprüfen Sie den übergeordneten Knoten
Da wir nun den spezifischen Knoten haben, können wir prüfen, ob sein übergeordneter Knoten mit dem Dokument selbst übereinstimmt. In diesem Beispiel vergleichen wir den übergeordneten Knoten mit dem Dokument mithilfe des Gleichheitsoperators (`==`) und zeigen Sie das Ergebnis an.

```csharp
Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
```

### Beispielquellcode zum Abrufen des übergeordneten Knotens mit Aspose.Words für .NET


```csharp
	Document doc = new Document();

	// Der Abschnitt ist der erste untergeordnete Knoten des Dokuments.
	Node section = doc.FirstChild;

	// Der übergeordnete Knoten des Abschnitts ist das Dokument.
	Console.WriteLine("Section parent is the document: " + (doc == section.ParentNode));
            
```

Dies ist ein vollständiges Codebeispiel zum Abrufen des übergeordneten Knotens eines bestimmten Knotens mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.
