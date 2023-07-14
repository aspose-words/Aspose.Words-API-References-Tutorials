---
title: Holen Sie sich Revisionstypen von Wörtern
linktitle: Holen Sie sich Revisionstypen von Wörtern
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erhalten Sie Revisionstypen von Wörtern in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/get-revision-types/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie mit Aspose.Words für .NET die Arten von Wortüberarbeitungen in einem Word-Dokument erhalten. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Überarbeitungen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Gehen Sie die Absätze durch

Als Nächstes gehen wir die Absätze des Dokuments durch und überprüfen die mit jedem Absatz verbundenen Worttypen.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Beispielquellcode für „Get Revision Types“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Abrufen von Revisionstypen in einem Dokument mit Aspose.Words für .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Arten von Wortüberarbeitungen in einem Word-Dokument erhält. Wir haben die Schritte befolgt, um das Dokument zu laden, die Absätze durchzugehen und die mit jedem Absatz verbundenen Arten von Wortüberprüfungen zu überprüfen. Jetzt können Sie dieses Wissen anwenden, um Wortüberprüfungen in Ihren eigenen Word-Dokumenten mit Aspose.Words für .NET zu analysieren.

### FAQs zum Abrufen von Revisionstypen von Wörtern

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

 A: Benutzen Sie die`Document` Klasse von Aspose.Words für .NET zum Laden eines Dokuments aus einer Datei. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie durchlaufe ich Absätze in einem Dokument in Aspose.Words für .NET?

 A: Benutzen Sie die`Paragraphs` Eigenschaft des Dokumentabschnitts, um die Sammlung von Absätzen abzurufen. Sie können dann eine Schleife verwenden, um jeden Absatz zu durchlaufen.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Verarbeiten Sie hier jeden Absatz
}
```

#### F: Wie kann ich überprüfen, ob ein Absatz in Aspose.Words für .NET verschoben (gelöscht) wurde?

 A: Verwenden Sie einen Absatz`IsMoveFromRevision` Eigenschaft, um zu überprüfen, ob sie verschoben (gelöscht) wurde.

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Der Absatz wurde verschoben (gelöscht)
}
```

#### F: Wie kann ich überprüfen, ob ein Absatz in Aspose.Words für .NET verschoben (eingefügt) wurde?

 A: Verwenden Sie einen Absatz`IsMoveToRevision`-Eigenschaft, um zu überprüfen, ob sie verschoben (eingefügt) wurde.

```csharp
if (paragraph.IsMoveToRevision)
{
     // Der Absatz wurde verschoben (eingefügt)
}
```