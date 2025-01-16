---
title: Doorhalen
linktitle: Doorhalen
second_title: Aspose.Words API voor documentverwerking
description: Leer hoe u doorhalingsopmaak toepast op tekst met Aspose.Words voor .NET met onze stapsgewijze handleiding. Verbeter uw vaardigheden in documentverwerking.
type: docs
weight: 10
url: /nl/net/working-with-markdown/strikethrough/
---
## Invoering

Welkom bij deze gedetailleerde gids over hoe u doorhalingsopmaak toepast op tekst met Aspose.Words voor .NET. Als u uw documentverwerkingsvaardigheden wilt verbeteren en een uniek tintje aan uw tekst wilt toevoegen, bent u hier aan het juiste adres. Laten we beginnen!

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

-  Aspose.Words voor .NET: Download het[hier](https://releases.aspose.com/words/net/).
- .NET Framework: Zorg ervoor dat .NET Framework op uw systeem is geïnstalleerd.
- Ontwikkelomgeving: Een IDE zoals Visual Studio.
- Basiskennis van C#: Kennis van C#-programmering is noodzakelijk.

## Naamruimten importeren

Om te beginnen moet u de benodigde namespaces importeren. Deze zijn essentieel voor toegang tot de Aspose.Words-bibliotheek en de functies ervan.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Initialiseer de DocumentBuilder

 De`DocumentBuilder` class is een krachtig hulpmiddel in Aspose.Words waarmee u eenvoudig inhoud aan uw document kunt toevoegen.

```csharp
// Initialiseer een DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Doorhalen-eigenschap instellen

Laten we nu de doorhalingseigenschap op onze tekst toepassen. Dit houdt in dat we de`StrikeThrough` eigendom van de`Font` bezwaar maken tegen`true`.

```csharp
// Maak de tekst doorstreept.
builder.Font.StrikeThrough = true;
```

## Stap 3: Schrijf tekst met doorhaling

 Nu de doorhalingseigenschap is ingesteld, kunnen we onze tekst toevoegen.`Writeln` De methode voegt de tekst toe aan het document.

```csharp
// Schrijf tekst met doorhaling.
builder.Writeln("This text will be StrikeThrough");
```

## Conclusie

En daar heb je het! Je hebt met succes doorhalingsopmaak toegevoegd aan je tekst met Aspose.Words voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor documentverwerking en -aanpassing. Of je nu rapporten, brieven of een ander type document maakt, het beheersen van deze functies zal ongetwijfeld je productiviteit en de kwaliteit van je output verbeteren.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars programmatisch Word-documenten kunnen maken, bewerken en converteren.

### Kan ik Aspose.Words voor .NET gebruiken in een commercieel project?
 Ja, u kunt Aspose.Words voor .NET gebruiken in commerciële projecten. Voor aankoopopties, bezoek de[koop pagina](https://purchase.aspose.com/buy).

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?
 Ja, u kunt een gratis proefversie downloaden[hier](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning voor Aspose.Words voor .NET?
 kunt ondersteuning krijgen van de Aspose-community en experts op het gebied van[ondersteuningsforum](https://forum.aspose.com/c/words/8).

### Kan ik andere tekstopmaakopties toepassen met Aspose.Words voor .NET?
Absoluut! Aspose.Words voor .NET ondersteunt een breed scala aan tekstopmaakopties, waaronder vet, cursief, onderstrepen en meer.