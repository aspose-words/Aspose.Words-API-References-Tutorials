---
title: Toegang tot herziene versie
linktitle: Toegang tot herziene versie
second_title: Aspose.Words-API voor documentverwerking
description: Krijg toegang tot een herziene versie van een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/access-revised-version/
---

In deze stapsgewijze handleiding laten we u zien hoe u toegang krijgt tot de herziene versie van een Word-document met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document laden

De eerste stap is het uploaden van het document met de revisies.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Stap 2: Toegang tot de herziene versie

We gaan nu verder met de herziene versie van het document.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Stap 3: Blader door revisies

Vervolgens doorlopen we de revisies die in het document aanwezig zijn en geven we specifieke informatie weer voor alinea's die lijstitems zijn.

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

### Voorbeeldbroncode voor Access Revised Version met Aspose.Words voor .NET

Hier is de volledige broncode voor toegang tot de herziene versie van een document met Aspose.Words voor .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Schakel over naar de herziene versie van het document.
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

## Conclusie

In deze zelfstudie hebben we geleerd hoe u toegang krijgt tot de herziene versie van een Word-document met Aspose.Words voor .NET. Door het document te laden, naar de herziene versie te navigeren en door de herzieningen te bladeren, konden we specifieke informatie verkrijgen voor paragrafen die lijstitems zijn. Aspose.Words voor .NET biedt krachtige functies voor het manipuleren van Word-documenten, inclusief toegang tot recensies. U kunt deze kennis nu gebruiken om toegang te krijgen tot de herziene versie van uw eigen Word-documenten met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe laad ik een document met revisies in Aspose.Words voor .NET?

 EEN: Gebruik de`Document`klasse van Aspose.Words voor .NET om een document te laden vanuit een bestand met revisies. U kunt het volledige documentpad opgeven.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Vraag: Hoe krijg ik toegang tot de herziene versie van een document in Aspose.Words voor .NET?

 EEN: Gebruik de`RevisionsView` eigendom van de`Document` bezwaar maken tegen toegang tot de herziene versie van het document. U kunt de waarde van de`RevisionsView`eigendom aan`RevisionsView.Final` om de definitieve versie zonder de revisies weer te geven.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Vraag: Hoe blader ik door documentrevisies in Aspose.Words voor .NET?

 EEN: Gebruik een`foreach` lus om de revisies in het document te doorlopen. U kunt gebruik maken van de`Revisions` eigendom van de`Document` object om een verzameling van alle revisies van het document te krijgen.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Verwerk elke revisie hier
}
```

#### Vraag: Hoe controleer ik of een alinea een lijstitem is in Aspose.Words voor .NET?

 EEN: Gebruik de`IsListItem` eigendom van de`Paragraph` object om te controleren of een alinea een lijstitem is. De`IsListItem` eigendommen retourneren`true` als de alinea een lijstitem is, wordt deze anders geretourneerd`false`.

```csharp
if (paragraph.IsListItem)
{
     // De alinea is een lijstitem
}
else
{
     // De alinea is geen lijstitem
}
```