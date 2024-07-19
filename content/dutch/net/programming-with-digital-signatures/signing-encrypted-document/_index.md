---
title: Gecodeerd Word-document ondertekenen
linktitle: Gecodeerd Word-document ondertekenen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u gecodeerde Word-documenten kunt ondertekenen met Aspose.Words voor .NET met deze gedetailleerde, stapsgewijze handleiding. Ideaal voor ontwikkelaars.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/signing-encrypted-document/
---
## Invoering

Heeft u zich ooit afgevraagd hoe u een gecodeerd Word-document ondertekent? Vandaag doorlopen we dit proces met Aspose.Words voor .NET. Zet je schrap en bereid je voor op een gedetailleerde, boeiende en leuke tutorial!

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat je alles hebt wat je nodig hebt:

1.  Aspose.Words voor .NET: downloaden en installeren vanaf[hier](https://releases.aspose.com/words/net/).
2. Visual Studio: Zorg ervoor dat u het hebt geïnstalleerd.
3. Een geldig certificaat: u heeft een .pfx-certificaatbestand nodig.
4. Basiskennis van C#: Als u de basisbeginselen begrijpt, wordt deze tutorial soepeler.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Deze zijn cruciaal voor toegang tot de functionaliteiten van Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Words.DigitalSignatures;
```

Laten we het proces nu opsplitsen in eenvoudige, beheersbare stappen.

## Stap 1: Uw project opzetten

Stel eerst uw Visual Studio-project in. Open Visual Studio en maak een nieuwe C#-consoletoepassing. Noem het iets beschrijvends, zoals "SignEncryptedWordDoc".

## Stap 2: Aspose.Words aan uw project toevoegen

Vervolgens moeten we Aspose.Words aan uw project toevoegen. Er zijn een paar manieren om dit te doen, maar het gebruik van NuGet is de eenvoudigste. 

1. Open de NuGet Package Manager-console via Extra > NuGet Package Manager > Package Manager-console.
2. Voer de volgende opdracht uit:

```powershell
Install-Package Aspose.Words
```

## Stap 3: De documentenmap voorbereiden

U hebt een map nodig waarin u uw Word-documenten en certificaten kunt opslaan. Laten we er een maken.

1. Maak een map op uw computer. Laten we het voor de eenvoud "DocumentDirectory" noemen.
2. Plaats uw Word-document (bijvoorbeeld "Document.docx") en uw .pfx-certificaat (bijvoorbeeld "morzal.pfx") in deze map.

## Stap 4: Het schrijven van de code

 Laten we nu in de code duiken. Open je`Program.cs` bestand en begin met het instellen van het pad naar uw documentmap en het initialiseren van het`SignOptions` met het decoderingswachtwoord.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };
```

## Stap 5: Het certificaat laden

 Laad vervolgens uw certificaat met behulp van de`CertificateHolder`klas. Hiervoor zijn het pad naar uw .pfx-bestand en het wachtwoord van het certificaat vereist.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Stap 6: Het document ondertekenen

 Gebruik ten slotte de`DigitalSignatureUtil.Sign` methode om uw gecodeerde Word-document te ondertekenen. Voor deze methode zijn het invoerbestand, het uitvoerbestand, de certificaathouder en de tekenopties vereist.

```csharp
DigitalSignatureUtil.Sign(
    dataDir + "Document.docx",
    dataDir + "DigitallySignedDocument.docx",
    certHolder,
    signOptions);
```

## Stap 7: De code uitvoeren

Sla uw bestand op en voer het project uit. Als alles correct is ingesteld, zou u uw ondertekende document in de opgegeven map moeten zien.

## Conclusie

En daar heb je het! U hebt met succes een gecodeerd Word-document ondertekend met Aspose.Words voor .NET. Met deze krachtige bibliotheek wordt digitaal ondertekenen een fluitje van een cent, zelfs voor gecodeerde bestanden. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik een ander type certificaat gebruiken?
Ja, Aspose.Words ondersteunt verschillende certificaattypen, zolang deze het juiste formaat hebben.

### Is het mogelijk om meerdere documenten tegelijk te ondertekenen?
Absoluut! U kunt een verzameling documenten doorlopen en elk document programmatisch ondertekenen.

### Wat moet ik doen als ik het decoderingswachtwoord vergeet?
Helaas kunt u zonder het decoderingswachtwoord het document niet ondertekenen.

### Kan ik een zichtbare handtekening aan het document toevoegen?
Ja, met Aspose.Words kunt u ook zichtbare digitale handtekeningen toevoegen.

### Is er een manier om de handtekening te verifiëren?
 Ja, u kunt gebruik maken van de`DigitalSignatureUtil.Verify` methode om handtekeningen te verifiëren.