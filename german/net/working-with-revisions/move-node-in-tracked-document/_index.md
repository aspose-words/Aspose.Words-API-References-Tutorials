---
title: Knoten im verfolgten Dokument verschieben
linktitle: Knoten im verfolgten Dokument verschieben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Verschieben Sie Knoten in einem verfolgten Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/move-node-in-tracked-document/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET einen Knoten in einem verfolgten Word-Dokument verschieben. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokument erstellen

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

## Schritt 2: Überarbeitungen nachverfolgen

Wir werden die Revisionsverfolgung im Dokument aktivieren.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Schritt 3: Verschieben Sie einen Knoten

Wir verschieben einen Knoten (Absatz) von einer Position an eine andere, während wir Revisionen generieren.

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

## Schritt 4: Beenden Sie die Verfolgung von Bewertungen

Wir werden die Nachverfolgung von Überarbeitungen im Dokument einstellen.

```csharp
doc.StopTrackRevisions();
```

## Schritt 5: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Beispielquellcode für „Node in Tracked Document verschieben“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Verschieben eines Knotens in einem verfolgten Dokument mit Aspose.Words für .NET:


```csharp
// Der Pfad zum Dokumentenverzeichnis.
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

// Generieren Sie Revisionen, wenn Sie einen Knoten von einem Ort an einen anderen verschieben.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Stoppen Sie den Prozess der Nachverfolgung von Revisionen.
doc.StopTrackRevisions();

// Es gibt 3 zusätzliche Absätze im Verschiebebereich.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET einen Knoten in einem verfolgten Word-Dokument verschiebt. Durch Befolgen der Schritte zum Erstellen des Dokuments, Aktivieren der Revisionsverfolgung, Verschieben des Knotens und Stoppen der Revisionsverfolgung konnten wir diese Manipulation erfolgreich durchführen. Aspose.Words für .NET ist ein leistungsstarkes Tool für die Textverarbeitung mit Word-Dokumenten und bietet erweiterte Funktionen zum Verwalten von Überarbeitungen. Jetzt können Sie dieses Wissen nutzen, um Knoten in Ihren eigenen Word-Dokumenten zu verschieben und gleichzeitig Revisionen mit Aspose.Words für .NET zu verfolgen.

### FAQs

#### F: Wie kann ich die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument aktivieren?

A: Um die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument zu aktivieren, können Sie die verwenden`StartTrackRevisions` Methode der`Document` Objekt. Diese Methode verwendet als Parameter den Namen des Autors der Revisionen und das Startdatum der Nachverfolgung der Revisionen.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### F: Wie kann ich einen Knoten in einem nachverfolgten Dokument verschieben, ohne Revisionen zu generieren?

 A: Wenn Sie einen Knoten in einem verfolgten Dokument verschieben möchten, ohne Revisionen zu generieren, können Sie das verwenden`Remove` Und`InsertAfter` oder`InsertBefore` Methoden der`Node` Objekt. Um beispielsweise einen Absatz nach dem anderen zu verschieben, können Sie den folgenden Code verwenden:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### F: Wie kann ich die Revisionsverfolgung in einem Aspose.Words für .NET-Dokument stoppen?

 A: Um die Nachverfolgung von Revisionen in einem Aspose.Words für .NET-Dokument zu stoppen, können Sie Folgendes verwenden`StopTrackRevisions` Methode der`Document` Objekt.

```csharp
doc.StopTrackRevisions();
```