---
title: Commentaar opgelost en antwoorden
linktitle: Commentaar opgelost en antwoorden
second_title: Aspose.Words-API voor documentverwerking
description: Automatiseer het oplossen en beantwoorden van opmerkingen in Word-documenten met Aspose.Words voor .NET. Stap-voor-stap handleiding inbegrepen.
type: docs
weight: 10
url: /nl/net/working-with-comments/comment-resolved-and-replies/
---
## Invoering

Als u met Word-documenten werkt, heeft u waarschijnlijk wel eens met opmerkingen te maken gehad. Ze zijn ideaal voor samenwerking, maar het beheren ervan kan lastig zijn. Met Aspose.Words voor .NET kunt u het proces van het oplossen en beantwoorden van opmerkingen automatiseren. Deze gids leidt u door de stappen om precies dat te doen.

## Vereisten

Zorg ervoor dat je het volgende bij je hebt voordat je erin duikt:

1.  Aspose.Words voor .NET: Je kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: ingesteld met .NET Framework.
3. Basiskennis van C#: Bekendheid met de syntaxis en concepten.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Dit zorgt ervoor dat alle klassen en methoden die we nodig hebben direct beschikbaar zijn.

```csharp
using Aspose.Words;
using Aspose.Words.Comments;
```

Laten we het proces opsplitsen in eenvoudige, gemakkelijk te volgen stappen. Elke stap helpt u de code en de functionaliteit ervan te begrijpen.

## Stap 1: Laad het document

 Laad om te beginnen het Word-document met de opmerkingen. Gebruik de`Document` klasse hiervoor.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

 Deze coderegel initialiseert een nieuw`Document` object met het pad naar uw Word-document.

## Stap 2: Opmerkingen ophalen

 Vervolgens moeten we alle opmerkingen in het document krijgen. Wij gebruiken de`GetChildNodes` methode om een verzameling op te halen`Comment` knooppunten.

```csharp
NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

Deze code haalt alle opmerkingen in het document op en slaat deze op in een`NodeCollection`.

## Stap 3: Open het oudercommentaar

Voor ons voorbeeld concentreren we ons op de eerste opmerking in de verzameling. Dit zal onze oudercommentaar zijn.

```csharp
Comment parentComment = (Comment)comments[0];
```

 Hier casten we het eerste knooppunt in de verzameling naar a`Comment` voorwerp.

## Stap 4: Loop door antwoorden

 Laten we nu de antwoorden op de bovenliggende opmerking doornemen. We gebruiken een`foreach` lus om elk antwoord te herhalen.

```csharp
foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

In deze lus afdrukken we de ID van de ouderopmerking en de status ervan (of deze nu klaar is of niet). Vervolgens markeren we elk antwoord als voltooid.

## Stap 5: Bewaar het document

Sla ten slotte het gewijzigde document op in uw map.

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

Deze code slaat de wijzigingen op in een nieuw document, zodat uw originele bestand onaangetast blijft.

## Conclusie

Het verwerken van opmerkingen in Word-documenten hoeft geen handmatig karwei te zijn. Met Aspose.Words voor .NET kunt u het proces automatiseren, waardoor u tijd bespaart en fouten vermindert. Volg deze handleiding om opmerkingen in uw documenten efficiënt op te lossen en te beantwoorden.

## Veelgestelde vragen

### Kan ik andere commentaargerelateerde taken automatiseren met Aspose.Words voor .NET?  
Ja, u kunt verschillende taken automatiseren, zoals het toevoegen, verwijderen en wijzigen van opmerkingen.

### Is Aspose.Words voor .NET compatibel met .NET Core?  
Ja, Aspose.Words voor .NET ondersteunt zowel .NET Framework als .NET Core.

### Hoe kan ik een gratis proefversie van Aspose.Words voor .NET krijgen?  
 U kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).

### Kan ik Aspose.Words voor .NET gebruiken om met andere documenttypen te werken?  
Ja, Aspose.Words ondersteunt verschillende formaten, waaronder DOCX, PDF, HTML en meer.

### Waar kan ik gedetailleerde documentatie vinden voor Aspose.Words voor .NET?  
 U heeft toegang tot de documentatie[hier](https://reference.aspose.com/words/net/).