---
title: Untergeordnete Knoten aufzählen
linktitle: Untergeordnete Knoten aufzählen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET untergeordnete Knoten in einem Absatz aufzählen.
type: docs
weight: 10
url: /de/net/working-with-node/enumerate-child-nodes/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der veranschaulicht, wie untergeordnete Knoten mithilfe von Aspose.Words für .NET aufgezählt werden.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Referenzen zur Verwendung von Aspose.Words für .NET in Ihr Projekt importiert haben. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## Schritt 2: Erstellen Sie ein neues Dokument
 In diesem Schritt erstellen wir ein neues Dokument mit`Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 3: Greifen Sie auf den Absatz und seine untergeordneten Knoten zu
 Um die untergeordneten Knoten eines Absatzes aufzuzählen, müssen wir zunächst auf den Absatz selbst zugreifen. Benutzen Sie die`GetChild` Methode mit der`Paragraph` Knotentyp, um den ersten Absatz des Dokuments abzurufen.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

Als nächstes rufen wir die Sammlung der untergeordneten Knoten des Absatzes mithilfe von ab`ChildNodes` Eigentum.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## Schritt 4: Untergeordnete Knoten durchsuchen
 Da wir nun die Sammlung untergeordneter Knoten haben, können wir sie mithilfe von a durchlaufen`foreach` Schleife. Wir überprüfen den Typ jedes untergeordneten Knotens und führen basierend auf dem Typ spezifische Operationen durch.

```csharp
foreach (Node child in children)
{
     // Ein Absatz kann untergeordnete Elemente verschiedener Typen enthalten, z. B. Läufe, Formen und andere.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 In diesem Beispiel prüfen wir, ob der untergeordnete Knoten vom Typ ist`Run` (zB ein Textfragment). Wenn ja, konvertieren wir den Knoten in`Run` und zeigen Sie den Text mit an`run.Text`.

## Beispielquellcode zum Aufzählen untergeordneter Knoten mit Aspose.Words für .NET


```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

NodeCollection children = paragraph.ChildNodes;
foreach (Node child in children)
{
	// Ein Absatz kann untergeordnete Elemente verschiedener Art enthalten, z. B. Läufe, Formen und andere.
	if (child.NodeType == NodeType.Run)
	{
		Run run = (Run) child;
		Console.WriteLine(run.Text);
	}
}
```

Dies ist ein vollständiges Codebeispiel zum Aufzählen der untergeordneten Knoten eines Absatzes mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die Referenzen importieren

