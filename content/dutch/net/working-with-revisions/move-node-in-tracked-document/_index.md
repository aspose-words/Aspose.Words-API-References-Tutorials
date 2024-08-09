---
title: Verplaats knooppunt in bijgehouden document
linktitle: Verplaats knooppunt in bijgehouden document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u knooppunten in een bijgehouden Word-document verplaatst met Aspose.Words voor .NET met onze gedetailleerde, stapsgewijze handleiding. Ideaal voor ontwikkelaars.
type: docs
weight: 10
url: /nl/net/working-with-revisions/move-node-in-tracked-document/
---
## Invoering

Hallo daar, Aspose.Words-enthousiastelingen! Als u ooit een knooppunt in een Word-document heeft moeten verplaatsen terwijl u revisies bijhoudt, bent u hier op de juiste plek. Vandaag duiken we in hoe we dit kunnen bereiken met Aspose.Words voor .NET. U leert niet alleen het stapsgewijze proces, maar u krijgt ook enkele tips en trucs om uw documentmanipulatie soepel en efficiënt te laten verlopen.

## Vereisten

Voordat we onze handen vuil maken met wat code, moeten we ervoor zorgen dat je alles hebt wat je nodig hebt:

-  Aspose.Words voor .NET: Download het[hier](https://releases.aspose.com/words/net/).
- .NET-omgeving: Zorg ervoor dat u een compatibele .NET-ontwikkelomgeving hebt ingesteld.
- Basiskennis C#: Deze tutorial gaat ervan uit dat je een basiskennis hebt van C#.

Heb je alles? Geweldig! Laten we verder gaan met de naamruimten die we moeten importeren.

## Naamruimten importeren

Allereerst moeten we de benodigde naamruimten importeren. Deze zijn essentieel voor het werken met Aspose.Words en het omgaan met documentknooppunten.

```csharp
using Aspose.Words;
using System;
```

Oké, laten we het proces opsplitsen in beheersbare stappen. Elke stap wordt gedetailleerd uitgelegd, zodat u begrijpt wat er op elk punt gebeurt.

## Stap 1: Initialiseer het document

 Om te beginnen moeten we een nieuw document initialiseren en a gebruiken`DocumentBuilder` om enkele paragrafen toe te voegen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Enkele paragrafen toevoegen
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// Controleer het initiële aantal alinea's
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Stap 2: Begin met het bijhouden van revisies

Vervolgens moeten we beginnen met het bijhouden van revisies. Dit is van cruciaal belang omdat we hierdoor de wijzigingen in het document kunnen zien.

```csharp
// Begin met het bijhouden van revisies
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Stap 3: Verplaats knooppunten

Nu komt het kerngedeelte van onze taak: een knooppunt van de ene locatie naar de andere verplaatsen. We verplaatsen de derde alinea en plaatsen deze vóór de eerste alinea.

```csharp
// Definieer het knooppunt dat moet worden verplaatst en het eindbereik ervan
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Verplaats de knooppunten binnen het gedefinieerde bereik
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## Stap 4: Stop met het bijhouden van revisies

Zodra we de knooppunten hebben verplaatst, moeten we stoppen met het bijhouden van revisies.

```csharp
// Houd op met het bijhouden van revisies
doc.StopTrackRevisions();
```

## Stap 5: Bewaar het document

Laten we ten slotte ons gewijzigde document opslaan in de opgegeven map.

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Voer het laatste aantal alinea's uit
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Conclusie

En daar heb je het! U hebt met succes een knooppunt in een bijgehouden document verplaatst met Aspose.Words voor .NET. Deze krachtige bibliotheek maakt het eenvoudig om Word-documenten programmatisch te manipuleren. Of u nu wijzigingen maakt, bewerkt of bijhoudt, Aspose.Words heeft de oplossing voor u. Dus ga je gang en probeer het eens. Veel codeerplezier!

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?

Aspose.Words voor .NET is een klassenbibliotheek voor het programmatisch werken met Word-documenten. Hiermee kunnen ontwikkelaars Word-documenten maken, bewerken, converteren en afdrukken binnen .NET-toepassingen.

### Hoe houd ik revisies in een Word-document bij met Aspose.Words?

 Om revisies bij te houden, gebruikt u de`StartTrackRevisions` methode op de`Document` voorwerp. Hierdoor wordt het bijhouden van revisies mogelijk, waarbij eventuele wijzigingen in het document worden weergegeven.

### Kan ik meerdere knooppunten verplaatsen in Aspose.Words?

Ja, je kunt meerdere knooppunten verplaatsen door ze te herhalen en methoden als`InsertBefore` of`InsertAfter` om ze op de gewenste locatie te plaatsen.

### Hoe stop ik met het bijhouden van revisies in Aspose.Words?

 Gebruik de`StopTrackRevisions` methode op de`Document` bezwaar maken tegen het bijhouden van revisies.

### Waar kan ik meer documentatie vinden over Aspose.Words voor .NET?

 U kunt gedetailleerde documentatie vinden[hier](https://reference.aspose.com/words/net/).