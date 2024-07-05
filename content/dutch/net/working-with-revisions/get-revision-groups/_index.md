---
title: Revisiegroepen ophalen
linktitle: Revisiegroepen ophalen
second_title: Aspose.Words-API voor documentverwerking
description: Ontvang revisiegroepen in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/get-revision-groups/
---

In deze stapsgewijze handleiding gaan we u vertellen hoe u de revisiegroepen in een Word-document kunt krijgen met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document laden

De eerste stap is het uploaden van het document met de revisies.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Stap 2: Blader door revisiegroepen

Vervolgens doorlopen we de revisiegroepen die in het document aanwezig zijn en geven we hun details weer, zoals auteur, revisietype en herziene tekst.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Voorbeeldbroncode voor Get Revision Groups met Aspose.Words voor .NET

Hier is de volledige broncode om de revisiegroepen in een document te krijgen met Aspose.Words voor .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de revisiegroepen in een Word-document kunt krijgen met Aspose.Words voor .NET. We hebben de stappen gevolgd om het document te laden en door de beoordelingsgroepen te bladeren, waarbij details zoals auteur en beoordelingstype worden weergegeven. U kunt deze kennis nu toepassen om revisies van uw eigen Word-document te analyseren met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe upload ik een document in Aspose.Words voor .NET?

 EEN: Gebruik de`Document` klasse van Aspose.Words voor .NET om een document uit een bestand te laden. U kunt het volledige documentpad opgeven.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Vraag: Hoe blader je door revisiegroepen in een document in Aspose.Words voor .NET?

 EEN: Gebruik de`Groups` eigendom van het document`Revisions`object om de verzameling revisiegroepen op te halen. U kunt vervolgens een lus gebruiken om elke beoordelingsgroep te doorlopen.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Verwerk hier elke beoordelingsgroep
}
```

#### Vraag: Hoe krijg ik de auteur van een recensiegroep in Aspose.Words voor .NET?

 EEN: Gebruik de`Author` eigendom van de`RevisionGroup` object om de auteur van de revisiegroep op te halen.

```csharp
string author = group.Author;
```

#### Vraag: Hoe krijg ik het revisietype van een revisiegroep in Aspose.Words voor .NET?

 EEN: Gebruik de`RevisionType` eigendom van de`RevisionGroup` object om het revisietype van de groep op te halen.

```csharp
string revisionType = group.RevisionType;
```