---
title: Ontvang revisietypes van woorden
linktitle: Ontvang revisietypes van woorden
second_title: Aspose.Words-API voor documentverwerking
description: Ontvang revisietypen van woorden in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/get-revision-types/
---

In deze stapsgewijze handleiding gaan we u vertellen hoe u de typen woordrevisies in een Word-document kunt krijgen met behulp van Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document laden

De eerste stap is het uploaden van het document met de revisies.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Stap 2: Blader door de paragrafen

Vervolgens lopen we de paragrafen van het document door en controleren we de typen woordrevisies die bij elke paragraaf horen.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Voorbeeldbroncode voor Get Revision Types met Aspose.Words voor .NET

Hier is de volledige broncode voor het ophalen van revisietypen in een document met Aspose.Words voor .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de typen woordrevisies in een Word-document kunt krijgen met behulp van Aspose.Words voor .NET. We hebben de stappen gevolgd om het document te laden, de paragrafen te doorlopen en de soorten woordrecensies te controleren die aan elke paragraaf zijn gekoppeld. Nu kunt u deze kennis toepassen om woordrecensies in uw eigen Word-documenten te analyseren met Aspose.Words voor .NET.

### Veelgestelde vragen over het verkrijgen van revisietypen van woorden

#### Vraag: Hoe upload ik een document in Aspose.Words voor .NET?

 EEN: Gebruik de`Document` klasse van Aspose.Words voor .NET om een document uit een bestand te laden. U kunt het volledige documentpad opgeven.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Vraag: Hoe loop ik door alinea's in een document in Aspose.Words voor .NET?

 EEN: Gebruik de`Paragraphs` eigenschap van de documentsectie om de verzameling alinea's op te halen. Je kunt dan een lus gebruiken om door elke alinea te lopen.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Verwerk hier elke paragraaf
}
```

#### Vraag: Hoe controleer ik of een alinea is verplaatst (verwijderd) in Aspose.Words voor .NET?

 A: Gebruik een paragraaf`IsMoveFromRevision` eigenschap om te controleren of deze is verplaatst (verwijderd).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // De paragraaf is verplaatst (verwijderd)
}
```

#### Vraag: Hoe controleer ik of een alinea is verplaatst (ingevoegd) in Aspose.Words voor .NET?

 A: Gebruik een paragraaf`IsMoveToRevision`eigenschap om te controleren of deze is verplaatst (ingevoegd).

```csharp
if (paragraph.IsMoveToRevision)
{
     // De paragraaf is verplaatst (ingevoegd)
}
```