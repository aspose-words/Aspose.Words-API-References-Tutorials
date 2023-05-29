---
title: Revisionstypen abrufen
linktitle: Revisionstypen abrufen
second_title: Aspose.Words für .NET API-Referenz
description: Erhalten Sie Revisionstypen in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/get-revision-types/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie mit Aspose.Words für .NET die Revisionstypen in einem Word-Dokument abrufen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Überarbeitungen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Gehen Sie die Absätze durch

Als Nächstes gehen wir die Absätze des Dokuments durch und überprüfen die mit jedem Absatz verbundenen Revisionstypen.

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
