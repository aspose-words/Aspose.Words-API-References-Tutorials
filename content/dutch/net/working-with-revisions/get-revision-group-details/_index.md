---
title: Details van de revisiegroep ophalen
linktitle: Details van de revisiegroep ophalen
second_title: Aspose.Words-API voor documentverwerking
description: Ontvang revisiegroepdetails in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/get-revision-group-details/
---

In deze stapsgewijze handleiding laten we u zien hoe u de details van een groep revisies in een Word-document kunt ophalen met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document laden

De eerste stap is het uploaden van het document met de revisies.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Stap 2: Blader door revisies

Vervolgens doorlopen we de revisies die in het document aanwezig zijn en geven we hun details weer, zoals type, auteur, datum en herziene tekst.

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


### Voorbeeldbroncode voor het ophalen van revisiegroepdetails met Aspose.Words voor .NET

Hier is de volledige broncode om de details van een groep revisies in een document te krijgen met behulp van Aspose.Words voor .NET:

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

## Conclusie

In deze zelfstudie hebben we geleerd hoe we de details van een groep revisies in een Word-document kunnen ophalen met behulp van Aspose.Words voor .NET. Door een lus en de juiste eigenschappen te gebruiken, konden we details weergeven zoals revisietype, auteur, datum en herziene tekst. Aspose.Words voor .NET biedt veel krachtige functies voor het manipuleren van Word-documenten, inclusief revisiebeheer. U kunt deze kennis nu gebruiken om revisiegroepdetails in uw eigen Word-documenten te krijgen met behulp van Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe laad ik een document met revisies in Aspose.Words voor .NET?

 EEN: Gebruik de`Document` klasse van Aspose.Words voor .NET om een document te laden vanuit een bestand met revisies. U kunt het volledige documentpad opgeven.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Vraag: Hoe krijg ik de details van een revisiegroep in Aspose.Words voor .NET?

A: Doorloop de revisies van het document met behulp van een lus en open de eigenschappen van elke revisie om de gewenste details te verkrijgen. U kunt gebruik maken van de`RevisionType`, `Author`, `DateTime`En`ParentNode` eigenschappen om respectievelijk het revisietype, de auteur, de datum en de herziene tekst te verkrijgen.

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

#### Vraag: Hoe controleer ik of een revisie tot een groep in Aspose.Words voor .NET behoort?

 EEN: Gebruik de`Group` eigendom van de`Revision` object om te controleren of een revisie tot een groep behoort. Als de`Group` eigendom is`null`betekent dit dat de revisie tot geen enkele groep behoort.

```csharp
if (revision.Group != null)
{
      // De revisie behoort tot een groep
}
else
{
      // De revisie behoort tot geen enkele groep
}
```