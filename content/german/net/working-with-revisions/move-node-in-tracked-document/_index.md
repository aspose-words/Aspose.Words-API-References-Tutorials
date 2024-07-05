---
title: Knoten im verfolgten Dokument verschieben
linktitle: Knoten im verfolgten Dokument verschieben
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Verschieben Sie Knoten in einem verfolgten Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/move-node-in-tracked-document/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET einen Knoten in einem verfolgten Word-Dokument verschieben. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Erstellen des Dokuments

Der erste Schritt besteht darin, ein neues Dokument zu erstellen und Absätze hinzuzufügen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Schritt 2: Revisionen verfolgen

Wir werden die Revisionsverfolgung im Dokument aktivieren.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Schritt 3: Verschieben eines Knotens

Wir werden beim Generieren von Revisionen einen Knoten (Absatz) von einer Position an eine andere verschieben.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Schritt 4: Beenden Sie die Bewertungsverfolgung

Wir werden die Nachverfolgung von Revisionen im Dokument beenden.

```csharp
doc.StopTrackRevisions();
```

## Schritt 5: Speichern des Dokuments

 Nach dem Einfügen des Texteingabeformularfelds speichern Sie das Dokument am gewünschten Speicherort mit dem`Save`Methode. Stellen Sie sicher, dass Sie den entsprechenden Dateipfad angeben:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Beispielquellcode für Move Node In Tracked Document mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Verschieben eines Knotens in einem verfolgten Dokument mit Aspose.Words für .NET:


```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Beginnen Sie mit der Nachverfolgung von Revisionen.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generieren Sie Revisionen, wenn Sie einen Knoten von einem Ort zum anderen verschieben.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Stoppen Sie die Verfolgung von Revisionen.
doc.StopTrackRevisions();

// Es gibt drei weitere Absätze im Move-From-Bereich.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET einen Knoten in einem verfolgten Word-Dokument verschiebt. Indem wir die Schritte zum Erstellen des Dokuments, Aktivieren der Revisionsverfolgung, Verschieben des Knotens und Stoppen der Revisionsverfolgung befolgten, konnten wir diese Manipulation erfolgreich durchführen. Aspose.Words für .NET ist ein leistungsstarkes Tool für die Textverarbeitung mit Word-Dokumenten und bietet erweiterte Funktionen zum Verwalten von Revisionen. Jetzt können Sie dieses Wissen nutzen, um Knoten in Ihren eigenen Word-Dokumenten zu verschieben, während Sie Revisionen mit Aspose.Words für .NET verfolgen.

### Häufig gestellte Fragen

#### F: Wie kann ich die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument aktivieren?

 A: Um die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument zu aktivieren, können Sie den`StartTrackRevisions` Methode der`Document` Objekt. Diese Methode verwendet als Parameter den Namen des Autors der Revisionen und das Startdatum der Nachverfolgung der Revisionen.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### F: Wie kann ich einen Knoten in einem verfolgten Dokument verschieben, ohne Revisionen zu generieren?

 A: Wenn Sie einen Knoten in einem verfolgten Dokument verschieben möchten, ohne Revisionen zu generieren, können Sie den`Remove` Und`InsertAfter` oder`InsertBefore` Methoden der`Node` Objekt. Um beispielsweise einen Absatz hinter einen anderen Absatz zu verschieben, können Sie den folgenden Code verwenden:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### F: Wie kann ich die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument stoppen?

 A: Um die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument zu beenden, können Sie den`StopTrackRevisions` Methode der`Document` Objekt.

```csharp
doc.StopTrackRevisions();
```