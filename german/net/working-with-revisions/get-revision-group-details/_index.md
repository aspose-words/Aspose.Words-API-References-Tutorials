---
title: Details zur Revisionsgruppe abrufen
linktitle: Details zur Revisionsgruppe abrufen
second_title: Aspose.Words für .NET API-Referenz
description: Erhalten Sie Revisionsgruppendetails in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/get-revision-group-details/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Details einer Gruppe von Revisionen in einem Word-Dokument abrufen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Überarbeitungen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Revisionen durchsuchen

Als Nächstes durchlaufen wir die im Dokument vorhandenen Überarbeitungen und zeigen deren Details an, z. B. Typ, Autor, Datum und überarbeiteter Text.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Beispielquellcode zum Abrufen von Revisionsgruppendetails mit Aspose.Words für .NET

Hier ist der vollständige Quellcode, um die Details einer Gruppe von Revisionen in einem Dokument mithilfe von Aspose.Words für .NET abzurufen:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach (Revision revision in doc.Revisions)
	{
		 string groupText = revision.Group != null
			 ? "Revision group text: " + revision.Group.Text
			 : "The revision does not belong to any group";

		 Console.WriteLine("Type: " + revision.RevisionType);
		 Console.WriteLine("Author: " + revision.Author);
		 Console.WriteLine("Date: " + revision.DateTime);
		 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
		 Console.WriteLine(groupText);
	}
	
```

