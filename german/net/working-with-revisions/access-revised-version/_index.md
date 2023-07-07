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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET auf die überarbeitete Version eines Word-Dokuments zugreift. Durch das Laden des Dokuments, das Navigieren zur überarbeiteten Version und das Durchsuchen der Revisionen konnten wir spezifische Informationen für Absätze abrufen, bei denen es sich um Listenelemente handelt. Aspose.Words für .NET bietet leistungsstarke Funktionen zum Bearbeiten von Word-Dokumenten, einschließlich Zugriff auf Rezensionen. Dieses Wissen können Sie nun nutzen, um mit Aspose.Words für .NET auf die überarbeitete Version Ihrer eigenen Word-Dokumente zuzugreifen.

### FAQs

#### F: Wie lade ich ein Dokument mit Revisionen in Aspose.Words für .NET?

 A: Benutzen Sie die`Document`Klasse von Aspose.Words für .NET zum Laden eines Dokuments aus einer Datei, die Revisionen enthält. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie greife ich in Aspose.Words für .NET auf die überarbeitete Version eines Dokuments zu?

 A: Benutzen Sie die`RevisionsView` Eigentum der`Document` Objekt, um auf die überarbeitete Version des Dokuments zuzugreifen. Sie können den Wert festlegen`RevisionsView` Eigentum zu`RevisionsView.Final` um die endgültige Version ohne die Überarbeitungen anzuzeigen.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### F: Wie durchsuche ich Dokumentrevisionen in Aspose.Words für .NET?

 A: Verwenden Sie a`foreach` Schleife, um die im Dokument vorhandenen Revisionen zu durchlaufen. Du kannst den ... benutzen`Revisions` Eigentum der`Document` Objekt, um eine Sammlung aller Revisionen des Dokuments abzurufen.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Verarbeiten Sie hier jede Revision
}
```

#### F: Wie überprüfe ich, ob ein Absatz ein Listenelement in Aspose.Words für .NET ist?

 A: Benutzen Sie die`IsListItem` Eigentum der`Paragraph` Objekt, um zu prüfen, ob ein Absatz ein Listenelement ist. Der`IsListItem` Immobilienrenditen`true` wenn der Absatz ein Listenelement ist, andernfalls wird zurückgegeben`false`.

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