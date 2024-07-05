---
title: Verplaats knooppunt in bijgehouden document
linktitle: Verplaats knooppunt in bijgehouden document
second_title: Aspose.Words-API voor documentverwerking
description: Verplaats knooppunten in een bijgehouden document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-revisions/move-node-in-tracked-document/
---

In deze stapsgewijze handleiding laten we u zien hoe u een knooppunt in een bijgehouden Word-document verplaatst met Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Het document aanmaken

De eerste stap is het maken van een nieuw document en het toevoegen van alinea's.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Stap 2: Houd revisies bij

We gaan het bijhouden van revisies in het document inschakelen.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Stap 3: Verplaats een knooppunt

We verplaatsen een knooppunt (paragraaf) van de ene positie naar de andere terwijl we revisies genereren.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Stap 4: Stop met het bijhouden van beoordelingen

We stoppen met het bijhouden van revisies in het document.

```csharp
doc.StopTrackRevisions();
```

## Stap 5: Het document opslaan

 Nadat u het tekstinvoerformulierveld hebt ingevoegd, slaat u het document op de gewenste locatie op met behulp van de`Save`methode. Zorg ervoor dat u het juiste bestandspad opgeeft:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Voorbeeldbroncode voor het verplaatsen van een knooppunt naar een bijgehouden document met behulp van Aspose.Words voor .NET

Hier is de volledige broncode voor het verplaatsen van een knooppunt in een bijgehouden document met Aspose.Words voor .NET:


```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Begin met het bijhouden van revisies.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Genereer revisies wanneer u een knooppunt van de ene locatie naar de andere verplaatst.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Stop het proces van het bijhouden van revisies.
doc.StopTrackRevisions();

// Er zijn 3 extra alinea's in het bereik 'Verplaatsen van'.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een knooppunt in een bijgehouden Word-document kunt verplaatsen met Aspose.Words voor .NET. Door de stappen te volgen voor het maken van het document, het inschakelen van het bijhouden van revisies, het verplaatsen van het knooppunt en het stoppen van het bijhouden van revisies, konden we deze manipulatie met succes uitvoeren. Aspose.Words voor .NET is een krachtig hulpmiddel voor het verwerken van woorden met Word-documenten en biedt geavanceerde functies voor het beheren van revisies. Nu kunt u deze kennis gebruiken om knooppunten in uw eigen Word-documenten te verplaatsen terwijl u revisies bijhoudt met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe kan ik het bijhouden van revisies inschakelen in een Aspose.Words voor .NET-document?

 A: Om het bijhouden van revisies in een Aspose.Words voor .NET-document in te schakelen, kunt u de`StartTrackRevisions` werkwijze van de`Document` voorwerp. Deze methode neemt als parameters de naam van de auteur van de revisies en de startdatum van de opvolging van de revisies.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Vraag: Hoe kan ik een knooppunt in een bijgehouden document verplaatsen zonder revisies te genereren?

 A: Als u een knooppunt in een bijgehouden document wilt verplaatsen zonder revisies te genereren, kunt u de`Remove` En`InsertAfter` of`InsertBefore` methoden van de`Node` voorwerp. Als u bijvoorbeeld een alinea na een andere alinea wilt verplaatsen, kunt u de volgende code gebruiken:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Vraag: Hoe kan ik het bijhouden van revisies in een Aspose.Words voor .NET-document stoppen?

 A: Om het bijhouden van revisies in een Aspose.Words voor .NET-document te stoppen, kunt u de`StopTrackRevisions` werkwijze van de`Document` voorwerp.

```csharp
doc.StopTrackRevisions();
```