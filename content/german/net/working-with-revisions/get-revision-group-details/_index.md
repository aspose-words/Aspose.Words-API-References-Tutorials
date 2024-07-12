---
title: Revisionsgruppendetails abrufen
linktitle: Revisionsgruppendetails abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erhalten Sie mit Aspose.Words für .NET Revisionsgruppendetails in einem Word-Dokument.
type: docs
weight: 10
url: /de/net/working-with-revisions/get-revision-group-details/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Details einer Gruppe von Revisionen in einem Word-Dokument abrufen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokument einlegen

Der erste Schritt besteht darin, das Dokument mit den Revisionen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Revisionen durchsuchen

Als Nächstes durchlaufen wir alle im Dokument vorhandenen Revisionen und zeigen ihre Details an, wie etwa Typ, Autor, Datum und überarbeiteten Text.

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


### Beispielquellcode für Get Revision Group Details mit Aspose.Words für .NET

Hier ist der vollständige Quellcode, um die Details einer Gruppe von Revisionen in einem Dokument mit Aspose.Words für .NET abzurufen:

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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Details einer Gruppe von Revisionen in einem Word-Dokument abruft. Durch die Verwendung einer Schleife und der entsprechenden Eigenschaften konnten wir Details wie Revisionstyp, Autor, Datum und überarbeiteten Text anzeigen. Aspose.Words für .NET bietet viele leistungsstarke Funktionen zum Bearbeiten von Word-Dokumenten, einschließlich Revisionsverwaltung. Sie können dieses Wissen nun nutzen, um mit Aspose.Words für .NET Details zu Revisionsgruppen in Ihre eigenen Word-Dokumente abzurufen.

### Häufig gestellte Fragen

#### F: Wie lade ich ein Dokument mit Revisionen in Aspose.Words für .NET?

 A: Verwenden Sie die`Document` Klasse von Aspose.Words für .NET, um ein Dokument aus einer Datei mit Revisionen zu laden. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie erhalte ich die Details einer Revisionsgruppe in Aspose.Words für .NET?

A: Gehen Sie die Revisionen des Dokuments in einer Schleife durch und greifen Sie auf die Eigenschaften jeder Revision zu, um die gewünschten Details zu erhalten. Sie können den`RevisionType`, `Author`, `DateTime`Und`ParentNode` Eigenschaften, um jeweils Revisionstyp, Autor, Datum und überarbeiteten Text abzurufen.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### F: Wie kann ich überprüfen, ob eine Revision zu einer Gruppe in Aspose.Words für .NET gehört?

 A: Verwenden Sie die`Group` Eigentum der`Revision` Objekt, um zu prüfen, ob eine Revision zu einer Gruppe gehört. Wenn das`Group` Eigentum ist`null`, bedeutet dies, dass die Revision zu keiner Gruppe gehört.

```csharp
if (revision.Group != null)
{
      // Die Revision gehört zu einer Gruppe
}
else
{
      // Die Revision gehört keiner Gruppe an
}
```