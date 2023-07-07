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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Revisionsgruppen in einem Word-Dokument abruft. Wir haben die Schritte zum Laden des Dokuments und zum Durchsuchen der Überprüfungsgruppen befolgt und dabei Details wie Autor und Überprüfungstyp angezeigt. Sie können dieses Wissen nun anwenden, um Revisionen Ihres eigenen Word-Dokuments mit Aspose.Words für .NET zu analysieren.

### FAQs

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

 A: Benutzen Sie die`Document` Klasse von Aspose.Words für .NET zum Laden eines Dokuments aus einer Datei. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie durchsuche ich Revisionsgruppen in einem Dokument in Aspose.Words für .NET?

 A: Benutzen Sie die`Groups` Eigentum des Dokuments`Revisions` Objekt, um die Sammlung von Revisionsgruppen abzurufen. Sie können dann eine Schleife verwenden, um jede Überprüfungsgruppe zu durchlaufen.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Bearbeiten Sie hier jede Bewertungsgruppe
}
```

#### F: Wie erhalte ich den Autor einer Überprüfungsgruppe in Aspose.Words für .NET?

 A: Benutzen Sie die`Author` Eigentum der`RevisionGroup` Objekt, um den Autor der Revisionsgruppe abzurufen.

```csharp
string author = group.Author;
```

#### F: Wie erhalte ich den Revisionstyp einer Revisionsgruppe in Aspose.Words für .NET?

 A: Benutzen Sie die`RevisionType` Eigentum der`RevisionGroup`Objekt, um den Revisionstyp der Gruppe abzurufen.

```csharp
string revisionType = group.RevisionType;
```