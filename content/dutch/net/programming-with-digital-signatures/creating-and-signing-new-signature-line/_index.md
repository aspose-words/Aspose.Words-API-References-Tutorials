---
title: Nieuwe handtekeningregel maken en ondertekenen
linktitle: Nieuwe handtekeningregel maken en ondertekenen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een handtekeningregel in een Word-document kunt maken en digitaal kunt ondertekenen met Aspose.Words voor .NET met deze stapsgewijze zelfstudie. Perfect voor documentautomatisering.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Invoering

Hallo daar! U hebt dus een Word-document en u moet een handtekeningregel toevoegen en het vervolgens digitaal ondertekenen. Klinkt lastig? Helemaal niet! Dankzij Aspose.Words voor .NET kunt u dit naadloos bereiken met slechts een paar regels code. In deze zelfstudie begeleiden we u door het hele proces, van het instellen van uw omgeving tot het opslaan van uw document met een glanzende nieuwe handtekening. Klaar? Laten we erin duiken!

## Vereisten

Voordat we ingaan op de code, zorgen we ervoor dat je alles hebt wat je nodig hebt:
1.  Aspose.Words voor .NET - Dat kan[download het hier](https://releases.aspose.com/words/net/).
2. Een .NET-ontwikkelomgeving - Visual Studio wordt sterk aanbevolen.
3. Een document om te ondertekenen - Maak een eenvoudig Word-document of gebruik een bestaand document.
4.  Een certificaatbestand - Dit is nodig voor digitale handtekeningen. U kunt gebruik maken van een`.pfx` bestand.
5. Afbeeldingen voor handtekeningregel - Optioneel een afbeeldingsbestand voor de handtekening.

## Naamruimten importeren

Eerst moeten we de benodigde naamruimten importeren. Deze stap is cruciaal omdat hiermee de omgeving wordt ingericht voor het gebruik van Aspose.Words-functionaliteiten.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Stap 1: De documentmap instellen

Elk project heeft een goede start nodig. Laten we het pad naar uw documentmap instellen. Hier worden uw documenten opgeslagen en opgehaald.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Een nieuw document maken

Laten we nu een nieuw Word-document maken met Aspose.Words. Dit wordt ons canvas waar we de handtekeninglijn toevoegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: De handtekeningregel invoegen

 Dit is waar de magie gebeurt. We voegen een handtekeningregel in ons document in met behulp van de`DocumentBuilder` klas.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Stap 4: Het document opslaan met de handtekeningregel

Zodra de handtekeningregel aanwezig is, moeten we het document opslaan. Dit is een tussenstap voordat we overgaan tot ondertekening.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Stap 5: Ondertekeningsopties instellen

Laten we nu de opties voor het ondertekenen van het document instellen. Dit omvat het opgeven van de handtekeningregel-ID en de te gebruiken afbeelding.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Stap 6: Het certificaat laden

Voor digitale handtekeningen is een certificaat vereist. Hier laden we het certificaatbestand dat zal worden gebruikt om het document te ondertekenen.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Stap 7: Het document ondertekenen

 Dit is de laatste stap. Wij gebruiken de`DigitalSignatureUtil`klas om het document te ondertekenen. Het ondertekende document wordt opgeslagen onder een nieuwe naam.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Conclusie

En daar heb je het! Met deze stappen hebt u met succes een nieuw Word-document gemaakt, een handtekeningregel toegevoegd en het digitaal ondertekend met Aspose.Words voor .NET. Het is een krachtige tool die documentautomatisering een fluitje van een cent maakt. Of u nu te maken heeft met contracten, overeenkomsten of andere formele documenten, deze methode zorgt ervoor dat ze veilig worden ondertekend en geauthenticeerd.

## Veelgestelde vragen

### Kan ik andere afbeeldingsformaten gebruiken voor de handtekeningregel?
Ja, u kunt verschillende afbeeldingsformaten gebruiken, zoals PNG, JPG, BMP, enz.

###  Is het nodig om een`.pfx` file for the certificate?
 Ja een`.pfx` bestand is een veelgebruikt formaat voor het opslaan van cryptografische informatie, waaronder certificaten en privésleutels.

### Kan ik meerdere handtekeningregels in één document toevoegen?
Absoluut! U kunt meerdere handtekeningregels invoegen door de invoegstap voor elke handtekening te herhalen.

### Wat moet ik doen als ik geen digitaal certificaat heb?
moet een digitaal certificaat verkrijgen van een vertrouwde certificeringsinstantie of er een genereren met behulp van tools zoals OpenSSL.

### Hoe verifieer ik de digitale handtekening in het document?
U kunt het ondertekende document in Word openen en naar de handtekeninggegevens gaan om de authenticiteit en integriteit van de handtekening te verifiëren.