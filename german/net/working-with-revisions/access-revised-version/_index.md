---
title: Greifen Sie auf die überarbeitete Version zu
linktitle: Greifen Sie auf die überarbeitete Version zu
second_title: Aspose.Words für .NET API-Referenz
description: Greifen Sie mit Aspose.Words für .NET auf eine überarbeitete Version eines Word-Dokuments zu.
type: docs
weight: 10
url: /de/net/working-with-revisions/access-revised-version/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET auf die überarbeitete Version eines Word-Dokuments zugreifen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Überarbeitungen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Schritt 2: Greifen Sie auf die überarbeitete Version zu

Wir werden nun mit der überarbeiteten Version des Dokuments fortfahren.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Schritt 3: Revisionen durchsuchen

Als Nächstes durchlaufen wir die im Dokument vorhandenen Überarbeitungen und zeigen spezifische Informationen für Absätze an, bei denen es sich um Listenelemente handelt.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Beispielquellcode für Access Revised Version mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den Zugriff auf die überarbeitete Version eines Dokuments mit Aspose.Words für .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Wechseln Sie zur überarbeiteten Version des Dokuments.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```


