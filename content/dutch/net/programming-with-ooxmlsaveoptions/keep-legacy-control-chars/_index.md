---
title: Bewaar oude controletekens
linktitle: Bewaar oude controletekens
second_title: Aspose.Words-API voor documentverwerking
description: Leer met deze stapsgewijze handleiding hoe u oudere stuurtekens in Word-documenten kunt behouden met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## Invoering

Bent u ooit verbaasd geweest over die vreemde, onzichtbare controletekens in uw Word-documenten? Het zijn net kleine, verborgen gremlins die de opmaak en functionaliteit kunnen verstoren. Gelukkig biedt Aspose.Words voor .NET een handige functie om deze verouderde stuurtekens intact te houden bij het opslaan van documenten. In deze zelfstudie gaan we dieper in op het beheren van deze controletekens met Aspose.Words voor .NET. We leggen het stap voor stap uit, zodat u onderweg elk detail begrijpt. klaar om te beginnen? Laten we erin duiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1.  Aspose.Words voor .NET: downloaden en installeren vanaf[hier](https://releases.aspose.com/words/net/).
2.  Een geldige Aspose-licentie: U kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
3. Ontwikkelomgeving: Visual Studio of een andere IDE die .NET ondersteunt.
4. Basiskennis van C#: Bekendheid met de programmeertaal C# is nuttig.

## Naamruimten importeren

Voordat u uw code schrijft, moet u de benodigde naamruimten importeren. Voeg de volgende regels toe bovenaan uw C#-bestand:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Uw project opzetten

Eerst moet u uw project instellen in Visual Studio (of uw favoriete IDE). 

1. Maak een nieuw C#-project: Open Visual Studio en maak een nieuw C# Console-toepassingsproject.
2. Installeer Aspose.Words voor .NET: Gebruik NuGet Package Manager om Aspose.Words voor .NET te installeren. Klik met de rechtermuisknop op uw project in Solution Explorer, selecteer 'NuGet-pakketten beheren', zoek naar 'Aspose.Words' en installeer het.

## Stap 2: Laad uw document

Vervolgens laadt u het Word-document dat de oude besturingstekens bevat.

1. Geef het documentpad op: Stel het pad naar uw documentmap in.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  Laad het document: Gebruik de`Document` klasse om uw document te laden.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## Stap 3: Configureer de opslagopties

Laten we nu de opslagopties configureren om de oude stuurtekens intact te houden.

1.  Creëer opslagopties: initialiseer een exemplaar van`OoxmlSaveOptions` en stel de`KeepLegacyControlChars`eigendom aan`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## Stap 4: Sla het document op

Sla ten slotte het document op met de geconfigureerde opslagopties.

1.  Sla het document op: Gebruik de`Save` werkwijze van de`Document` class om het document op te slaan met de opgegeven opslagopties.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## Conclusie

En daar heb je het! Door deze stappen te volgen, kunt u ervoor zorgen dat uw oude stuurtekens behouden blijven wanneer u met Word-documenten werkt in Aspose.Words voor .NET. Deze functie kan een redder in nood zijn, vooral als het gaat om complexe documenten waarbij controlekarakters een cruciale rol spelen. 

## Veelgestelde vragen

### Wat zijn oudere controlekarakters?

Verouderde besturingstekens zijn niet-afdrukbare tekens die in oudere documenten worden gebruikt om de opmaak en lay-out te bepalen.

### Kan ik deze controletekens verwijderen in plaats van ze te behouden?

Ja, u kunt Aspose.Words voor .NET gebruiken om deze tekens indien nodig te verwijderen of te vervangen.

### Is deze functie beschikbaar in alle versies van Aspose.Words voor .NET?

Deze functie is beschikbaar in recente versies. Zorg ervoor dat u de nieuwste versie gebruikt om toegang te krijgen tot alle functionaliteiten.

### Heb ik een licentie nodig om Aspose.Words voor .NET te gebruiken?

 Ja, u heeft een geldige licentie nodig. U kunt een tijdelijke licentie krijgen voor evaluatiedoeleinden[hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik meer documentatie vinden over Aspose.Words voor .NET?

 U kunt gedetailleerde documentatie vinden[hier](https://reference.aspose.com/words/net/).
 