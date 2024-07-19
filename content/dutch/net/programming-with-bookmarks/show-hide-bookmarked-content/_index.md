---
title: Toon inhoud met bladwijzer verbergen in Word-document
linktitle: Toon inhoud met bladwijzer verbergen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u inhoud met een bladwijzer in Word-documenten kunt weergeven en verbergen met Aspose.Words voor .NET met deze gedetailleerde, stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Invoering

Klaar om in de wereld van documentmanipulatie te duiken met Aspose.Words voor .NET? Of u nu een ontwikkelaar bent die documenttaken wil automatiseren of gewoon iemand die nieuwsgierig is naar het programmatisch omgaan met Word-bestanden, u bent op de juiste plek. Vandaag onderzoeken we hoe u inhoud met een bladwijzer in een Word-document kunt weergeven en verbergen met Aspose.Words voor .NET. Met deze stapsgewijze handleiding wordt u een professional in het beheren van de zichtbaarheid van inhoud op basis van bladwijzers. Laten we beginnen!

## Vereisten

Voordat we ingaan op de kern van de zaak, zijn er een paar dingen die je nodig hebt:

1. Visual Studio: elke versie die compatibel is met .NET.
2.  Aspose.Words voor .NET: Download het[hier](https://releases.aspose.com/words/net/).
3. Basiskennis van C#: Als u een eenvoudig "Hello World"-programma kunt schrijven, bent u klaar om te gaan.
4. Een Word-document met bladwijzers: voor deze zelfstudie gebruiken we een voorbeelddocument met bladwijzers.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Dit zorgt ervoor dat we over alle hulpmiddelen beschikken die we nodig hebben voor onze taak.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Nu deze naamruimten aanwezig zijn, zijn we helemaal klaar om aan onze reis te beginnen.

## Stap 1: Uw project opzetten

Oké, laten we beginnen met het opzetten van ons project in Visual Studio.

### Maak een nieuw project

Open Visual Studio en maak een nieuw Console App-project (.NET Core). Noem het iets pakkends, zoals "BookmarkVisibilityManager".

### Voeg Aspose.Words toe voor .NET

U moet Aspose.Words voor .NET aan uw project toevoegen. U kunt dit doen via NuGet Package Manager.

1. Ga naar Extra > NuGet-pakketbeheer > NuGet-pakketten voor oplossing beheren.
2. Zoek naar "Aspose.Words".
3. Installeer het pakket.

Geweldig! Nu ons project is opgezet, gaan we verder met het laden van ons document.

## Stap 2: Het document laden

We moeten het Word-document laden dat de bladwijzers bevat. Voor deze zelfstudie gebruiken we een voorbeelddocument met de naam 'Bookmarks.docx'.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Dit codefragment stelt het pad naar uw documentmap in en laadt het document in de`doc` voorwerp.

## Stap 3: Gemarkeerde inhoud tonen/verbergen

Nu komt het leuke gedeelte: de inhoud weergeven of verbergen op basis van bladwijzers. We zullen een methode maken genaamd`ShowHideBookmarkedContent` om dit af te handelen.

Hier is de methode waarmee u de zichtbaarheid van inhoud met een bladwijzer kunt wijzigen:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Uitsplitsing van de methode

-  Bladwijzer ophalen:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` haalt de bladwijzer op.
- Knooppuntdoorgang: We doorkruisen de knooppunten binnen de bladwijzer.
-  Zichtbaarheid wisselen: als het knooppunt een`Run` (een aaneengesloten stuk tekst), stellen we de waarde ervan in`Hidden` eigendom.

## Stap 4: De methode toepassen

Laten we, nu we onze methode hebben ingevoerd, deze toepassen om inhoud op basis van een bladwijzer weer te geven of te verbergen.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Deze coderegel verbergt de inhoud in de bladwijzer met de naam "MyBookmark1".

## Stap 5: Het document opslaan

Laten we ten slotte ons gewijzigde document opslaan.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Hiermee wordt het document opgeslagen met de wijzigingen die we hebben aangebracht.

## Conclusie

En daar heb je het! U hebt zojuist geleerd hoe u inhoud met een bladwijzer in een Word-document kunt weergeven en verbergen met Aspose.Words voor .NET. Met deze krachtige tool wordt het manipuleren van documenten een fluitje van een cent, of u nu rapporten automatiseert, sjablonen maakt of gewoon aan Word-bestanden sleutelt. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik meerdere bladwijzers tegelijk schakelen?
 Ja, u kunt bellen met de`ShowHideBookmarkedContent` methode voor elke bladwijzer die u wilt wijzigen.

### Heeft het verbergen van inhoud invloed op de structuur van het document?
Nee, het verbergen van inhoud heeft alleen invloed op de zichtbaarheid ervan. De inhoud blijft in het document.

### Kan ik deze methode gebruiken voor andere soorten inhoud?
Deze methode schakelt specifiek tekstuitvoeringen in of uit. Voor andere inhoudstypen moet u de logica voor het doorlopen van knooppunten wijzigen.

### Is Aspose.Words voor .NET gratis?
 Aspose.Words biedt een gratis proefperiode[hier](https://releases.aspose.com/) , maar voor productiegebruik is een volledige licentie vereist. Je kunt het kopen[hier](https://purchase.aspose.com/buy).

### Hoe kan ik ondersteuning krijgen als ik problemen tegenkom?
 U kunt ondersteuning krijgen van de Aspose-gemeenschap[hier](https://forum.aspose.com/c/words/8).