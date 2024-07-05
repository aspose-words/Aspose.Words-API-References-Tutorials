---
title: Zugriff auf überarbeitete Version
linktitle: Zugriff auf überarbeitete Version
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Greifen Sie mit Aspose.Words für .NET auf eine überarbeitete Version eines Word-Dokuments zu.
type: docs
weight: 10
url: /de/net/working-with-revisions/access-revised-version/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET auf die überarbeitete Version eines Word-Dokuments zugreifen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokument einlegen

Der erste Schritt besteht darin, das Dokument mit den Revisionen hochzuladen.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Schritt 2: Zugriff auf die überarbeitete Version

Wir kommen nun zur überarbeiteten Version des Dokuments.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Schritt 3: Revisionen durchsuchen

Als Nächstes durchlaufen wir alle im Dokument vorhandenen Revisionen und zeigen spezifische Informationen für Absätze an, bei denen es sich um Listenelemente handelt.

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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET auf die überarbeitete Version eines Word-Dokuments zugreift. Indem wir das Dokument geladen, zur überarbeiteten Version navigiert und die Überarbeitungen durchsucht haben, konnten wir spezifische Informationen zu Absätzen abrufen, die Listenelemente sind. Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Word-Dokumenten, einschließlich des Zugriffs auf Überarbeitungen. Dieses Wissen können Sie nun nutzen, um mit Aspose.Words für .NET auf die überarbeitete Version Ihrer eigenen Word-Dokumente zuzugreifen.

### Häufig gestellte Fragen

#### F: Wie lade ich ein Dokument mit Revisionen in Aspose.Words für .NET?

 A: Verwenden Sie die`Document` Klasse von Aspose.Words für .NET, um ein Dokument aus einer Datei mit Revisionen zu laden. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie greife ich in Aspose.Words für .NET auf die überarbeitete Version eines Dokuments zu?

 A: Verwenden Sie die`RevisionsView` Eigentum der`Document` Objekt, um auf die überarbeitete Version des Dokuments zuzugreifen. Sie können den Wert des`RevisionsView`Eigentum an`RevisionsView.Final` um die endgültige Version ohne die Überarbeitungen anzuzeigen.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### F: Wie durchsuche ich Dokumentrevisionen in Aspose.Words für .NET?

A: Verwenden Sie ein`foreach` Schleife, um durch die im Dokument vorhandenen Revisionen zu iterieren. Sie können die`Revisions` Eigentum der`Document` Objekt, um eine Sammlung aller Revisionen des Dokuments zu erhalten.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Bearbeiten Sie hier jede Revision
}
```

#### F: Wie kann ich in Aspose.Words für .NET überprüfen, ob ein Absatz ein Listenelement ist?

 A: Verwenden Sie die`IsListItem` Eigentum der`Paragraph` Objekt, um zu prüfen, ob ein Absatz ein Listenelement ist. Das`IsListItem` Immobilienrenditen`true` wenn der Absatz ein Listenelement ist, andernfalls wird zurückgegeben`false`.

```csharp
if (paragraph.IsListItem)
{
     // Der Absatz ist ein Listenelement
}
else
{
     // Der Absatz ist kein Listenelement
}
```