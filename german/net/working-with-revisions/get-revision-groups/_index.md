---
title: Revisionsgruppen abrufen
linktitle: Revisionsgruppen abrufen
second_title: Aspose.Words für .NET API-Referenz
description: Erhalten Sie Revisionsgruppen in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/get-revision-groups/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie mit Aspose.Words für .NET die Revisionsgruppen in ein Word-Dokument abrufen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Überarbeitungen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Revisionsgruppen durchsuchen

Als Nächstes durchlaufen wir die im Dokument vorhandenen Revisionsgruppen und zeigen deren Details an, z. B. Autor, Revisionstyp und überarbeiteten Text.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Beispielquellcode für Get Revision Groups mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Abrufen der Revisionsgruppen in einem Dokument mit Aspose.Words für .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```


