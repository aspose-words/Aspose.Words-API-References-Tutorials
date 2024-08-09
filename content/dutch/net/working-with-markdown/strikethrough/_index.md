---
title: Doorhalen
linktitle: Doorhalen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u doorhalingsopmaak op tekst toepast met Aspose.Words voor .NET met onze stapsgewijze handleiding. Verbeter uw vaardigheden op het gebied van documentverwerking.
type: docs
weight: 10
url: /nl/net/working-with-markdown/strikethrough/
---
## Invoering

Welkom bij deze gedetailleerde handleiding over het toepassen van doorgehaalde opmaak op tekst met behulp van Aspose.Words voor .NET. Als u uw vaardigheden op het gebied van documentverwerking wilt verbeteren en een uniek tintje aan uw tekst wilt toevoegen, bent u hier aan het juiste adres. Laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

-  Aspose.Words voor .NET: Download het[hier](https://releases.aspose.com/words/net/).
- .NET Framework: Zorg ervoor dat .NET Framework op uw systeem is geïnstalleerd.
- Ontwikkelomgeving: een IDE zoals Visual Studio.
- Basiskennis van C#: Bekendheid met programmeren in C# is noodzakelijk.

## Naamruimten importeren

Om te beginnen moet u de benodigde naamruimten importeren. Deze zijn essentieel voor toegang tot de Aspose.Words-bibliotheek en zijn functies.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Initialiseer DocumentBuilder

 De`DocumentBuilder` class is een krachtig hulpmiddel in Aspose.Words waarmee u eenvoudig inhoud aan uw document kunt toevoegen.

```csharp
// Initialiseer een DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Doorstreep-eigenschap instellen

Laten we nu de eigenschap doorhalen op onze tekst toepassen. Dit omvat het instellen van de`StrikeThrough` eigendom van de`Font` bezwaar tegen`true`.

```csharp
// Maak de tekst doorgehaald.
builder.Font.StrikeThrough = true;
```

## Stap 3: Schrijf tekst met doorhaling

 Nu de eigenschap doorhalen is ingesteld, kunnen we nu onze tekst toevoegen. De`Writeln` methode voegt de tekst aan het document toe.

```csharp
// Schrijf tekst met doorhalen.
builder.Writeln("This text will be StrikeThrough");
```

## Conclusie

En daar heb je het! U hebt met succes doorgehaalde opmaak aan uw tekst toegevoegd met Aspose.Words voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor documentverwerking en maatwerk. Of u nu rapporten, brieven of enig ander type document maakt, het beheersen van deze functies zal ongetwijfeld uw productiviteit en de kwaliteit van uw output verbeteren.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en converteren.

### Kan ik Aspose.Words voor .NET gebruiken in een commercieel project?
 Ja, u kunt Aspose.Words voor .NET gebruiken in commerciële projecten. Voor aankoopmogelijkheden, bezoek de[pagina kopen](https://purchase.aspose.com/buy).

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?
 Ja, u kunt een gratis proefversie downloaden[hier](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning voor Aspose.Words voor .NET?
 kunt ondersteuning krijgen van de Aspose-gemeenschap en experts op het gebied van[ondersteuningsforum](https://forum.aspose.com/c/words/8).

### Kan ik andere tekstopmaakopties toepassen met Aspose.Words voor .NET?
Absoluut! Aspose.Words voor .NET ondersteunt een breed scala aan opties voor tekstopmaak, waaronder vet, cursief, onderstrepen en meer.