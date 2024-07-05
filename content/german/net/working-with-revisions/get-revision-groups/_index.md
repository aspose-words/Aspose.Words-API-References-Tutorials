---
title: Revisionsgruppen abrufen
linktitle: Revisionsgruppen abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Holen Sie sich Revisionsgruppen in ein Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-revisions/get-revision-groups/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie mit Aspose.Words für .NET die Revisionsgruppen in einem Word-Dokument erhalten. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokument einlegen

Der erste Schritt besteht darin, das Dokument mit den Revisionen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Revisionsgruppen durchsuchen

Als Nächstes durchlaufen wir alle im Dokument vorhandenen Revisionsgruppen und zeigen ihre Details an, beispielsweise Autor, Revisionstyp und überarbeiteten Text.

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

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Revisionsgruppen in einem Word-Dokument erhält. Wir haben die Schritte befolgt, um das Dokument zu laden und die Revisionsgruppen zu durchsuchen, wobei Details wie Autor und Revisionstyp angezeigt werden. Sie können dieses Wissen nun anwenden, um Revisionen Ihres eigenen Word-Dokuments mit Aspose.Words für .NET zu analysieren.

### Häufig gestellte Fragen

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

 A: Verwenden Sie die`Document` Klasse von Aspose.Words für .NET, um ein Dokument aus einer Datei zu laden. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie durchsuche ich Revisionsgruppen in einem Dokument in Aspose.Words für .NET?

 A: Verwenden Sie die`Groups` Eigenschaft des Dokuments`Revisions`-Objekt, um die Sammlung der Revisionsgruppen abzurufen. Sie können dann eine Schleife verwenden, um jede einzelne Revisionsgruppe zu durchlaufen.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Bearbeiten Sie hier jede Überprüfungsgruppe
}
```

#### F: Wie erhalte ich den Autor einer Überprüfungsgruppe in Aspose.Words für .NET?

 A: Verwenden Sie die`Author` Eigentum der`RevisionGroup` Objekt, um den Autor der Revisionsgruppe abzurufen.

```csharp
string author = group.Author;
```

#### F: Wie erhalte ich den Revisionstyp einer Revisionsgruppe in Aspose.Words für .NET?

 A: Verwenden Sie die`RevisionType` Eigentum der`RevisionGroup` Objekt, um den Revisionstyp der Gruppe abzurufen.

```csharp
string revisionType = group.RevisionType;
```