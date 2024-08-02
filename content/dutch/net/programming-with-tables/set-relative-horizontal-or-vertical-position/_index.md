---
title: Stel de relatieve horizontale of verticale positie in
linktitle: Stel de relatieve horizontale of verticale positie in
second_title: Aspose.Words-API voor documentverwerking
description: Leer met deze stapsgewijze handleiding hoe u relatieve horizontale en verticale posities instelt voor tabellen in Word-documenten met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---
## Invoering

Ooit het gevoel gehad dat u vastliep bij het positioneren van tabellen zoals u dat wilt in uw Word-documenten? Nou, je bent niet de enige. Of u nu een professioneel rapport of een stijlvolle brochure maakt, het uitlijnen van tabellen kan een wereld van verschil maken. Dat is waar Aspose.Words voor .NET van pas komt. In deze zelfstudie leert u stapsgewijs hoe u relatieve horizontale of verticale posities instelt voor tabellen in uw Word-documenten. Laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1.  Aspose.Words voor .NET: Als je dat nog niet hebt gedaan, kun je het downloaden[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere .NET-compatibele IDE.
3. Basiskennis van C#: In deze tutorial wordt ervan uitgegaan dat u bekend bent met de basisprincipes van programmeren in C#.

## Naamruimten importeren

Allereerst moet u de benodigde naamruimten importeren. Dit is essentieel voor toegang tot de functionaliteiten van Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Stap 1: Laad uw document

Om aan de slag te gaan, moet u uw Word-document in het programma laden. Hier ziet u hoe u het kunt doen:

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Dit codefragment stelt het pad naar uw documentmap in en laadt het specifieke document waaraan u wilt werken. Zorg ervoor dat uw documentpad correct is om laadproblemen te voorkomen.

## Stap 2: Toegang tot de tabel

Vervolgens moeten we toegang krijgen tot de tabel in het document. Normaal gesproken wilt u werken met de eerste tabel in de hoofdsectie.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

Deze coderegel haalt de eerste tabel op uit de hoofdtekst van het document. Als uw document meerdere tabellen bevat, kunt u de index dienovereenkomstig aanpassen.

## Stap 3: Stel de horizontale positie in

Laten we nu de horizontale positie van de tabel instellen ten opzichte van een specifiek element. In dit voorbeeld positioneren we het ten opzichte van de kolom.

```csharp
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
```

 Door het instellen van de`HorizontalAnchor` naar`RelativeHorizontalPosition.Column`, geeft u aan dat de tabel zichzelf horizontaal moet uitlijnen ten opzichte van de kolom waarin deze zich bevindt.

## Stap 4: Stel de verticale positie in

Net als bij horizontale positionering kunt u ook de verticale positie instellen. Hier positioneren we het ten opzichte van de pagina.

```csharp
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Het instellen van de`VerticalAnchor` naar`RelativeVerticalPosition.Page` zorgt ervoor dat de tabel verticaal is uitgelijnd volgens de pagina.

## Stap 5: Bewaar uw document

Sla ten slotte uw wijzigingen op in een nieuw document. Dit is een cruciale stap om ervoor te zorgen dat uw wijzigingen behouden blijven.

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Met deze opdracht wordt het gewijzigde document opgeslagen onder een nieuwe naam, zodat u uw originele bestand niet overschrijft.

## Conclusie

En daar heb je het! U hebt met succes de relatieve horizontale en verticale posities voor een tabel in een Word-document ingesteld met Aspose.Words voor .NET. Met deze nieuwe vaardigheid kunt u de lay-out en leesbaarheid van uw documenten verbeteren, waardoor ze er professioneler en verzorgder uitzien. Blijf experimenteren met verschillende posities en kijk wat het beste werkt voor jouw behoeften.

## Veelgestelde vragen

### Kan ik tabellen positioneren ten opzichte van andere elementen?  
Ja, met Aspose.Words kunt u tabellen positioneren ten opzichte van verschillende elementen, zoals marges, pagina's, kolommen en meer.

### Heb ik een licentie nodig om Aspose.Words voor .NET te gebruiken?  
 Ja, u kunt een licentie kopen[hier](https://purchase.aspose.com/buy) of vraag een tijdelijke licentie aan[hier](https://purchase.aspose.com/temporary-license/).

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?  
 Absoluut! U kunt een gratis proefversie downloaden[hier](https://releases.aspose.com/).

### Kan ik Aspose.Words met andere programmeertalen gebruiken?  
Aspose.Words is voornamelijk ontworpen voor .NET, maar er zijn versies beschikbaar voor Java, Python en andere platforms.

### Waar kan ik meer gedetailleerde documentatie vinden?  
Raadpleeg de Aspose.Words-documentatie voor meer diepgaande informatie[hier](https://reference.aspose.com/words/net/).