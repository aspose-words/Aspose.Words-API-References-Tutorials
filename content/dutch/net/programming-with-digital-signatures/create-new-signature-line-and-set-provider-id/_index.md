---
title: Maak een nieuwe handtekeningregel en stel de provider-ID in
linktitle: Maak een nieuwe handtekeningregel en stel de provider-ID in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een nieuwe handtekeningregel maakt en de provider-ID in Word-documenten instelt met Aspose.Words voor .NET. Stap-voor-stap handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Invoering

Hallo daar, tech-enthousiastelingen! Heeft u zich ooit afgevraagd hoe u programmatisch een handtekeningregel aan uw Word-documenten kunt toevoegen? Welnu, vandaag duiken we daar precies in met behulp van Aspose.Words voor .NET. Deze handleiding begeleidt u bij elke stap, waardoor u heel eenvoudig een nieuwe handtekeningregel kunt maken en de provider-ID in uw Word-documenten kunt instellen. Of u nu de documentverwerking automatiseert of gewoon uw workflow wilt stroomlijnen, deze tutorial heeft de oplossing voor u.

## Vereisten

Voordat we onze handen vuil maken, moeten we ervoor zorgen dat we alles hebben wat we nodig hebben:

1.  Aspose.Words voor .NET: Download het als je dat nog niet hebt gedaan[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere C#-ontwikkelomgeving.
3. .NET Framework: Zorg ervoor dat .NET Framework is geïnstalleerd.
4. PFX-certificaat: Voor het ondertekenen van documenten heeft u een PFX-certificaat nodig. U kunt er een verkrijgen bij een vertrouwde certificeringsinstantie.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten in uw C#-project importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Oké, laten we tot de kern van de zaak komen. Hier vindt u een gedetailleerd overzicht van elke stap voor het maken van een nieuwe handtekeningregel en het instellen van de provider-ID.

## Stap 1: Maak een nieuw document

Om te beginnen moeten we een nieuw Word-document maken. Dit zal het canvas zijn voor onze kenmerkende lijn.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In dit fragment initialiseren we een nieuw`Document` en een`DocumentBuilder` . De`DocumentBuilder` helpt ons elementen aan ons document toe te voegen.

## Stap 2: Definieer handtekeninglijnopties

Vervolgens definiëren we de opties voor onze handtekeningregel. Dit omvat de naam, titel, e-mail en andere details van de ondertekenaar.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Deze opties personaliseren de handtekeningregel, waardoor deze duidelijk en professioneel wordt.

## Stap 3: Voeg de handtekeningregel in

Nu onze opties zijn ingesteld, kunnen we nu de handtekeningregel in het document invoegen.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Hier, de`InsertSignatureLine` methode voegt de handtekeningregel toe en we wijzen er een unieke provider-ID aan toe.

## Stap 4: Sla het document op

Nadat we de handtekeningregel hebben ingevoegd, slaan we het document op.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Hiermee wordt uw document opgeslagen met de nieuw toegevoegde handtekeningregel.

## Stap 5: Ondertekeningsopties instellen

Nu moeten we de opties instellen voor het ondertekenen van het document. Dit omvat de handtekeningregel-ID, provider-ID, opmerkingen en de ondertekentijd.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Deze opties zorgen ervoor dat het document met de juiste gegevens wordt ondertekend.

## Stap 6: Certificaathouder aanmaken

Om het document te ondertekenen, gebruiken we een PFX-certificaat. Laten we er een certificaathouder voor aanmaken.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Zorg ervoor dat u vervangt`"morzal.pfx"` met uw daadwerkelijke certificaatbestand en`"aw"` met uw certificaatwachtwoord.

## Stap 7: Onderteken het document

Ten slotte ondertekenen we het document met behulp van het hulpprogramma voor digitale handtekeningen.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Hiermee wordt het document ondertekend en opgeslagen als een nieuw bestand.

## Conclusie

En daar heb je het! U hebt met succes een nieuwe handtekeningregel gemaakt en de provider-ID ingesteld in een Word-document met Aspose.Words voor .NET. Deze krachtige bibliotheek maakt het ongelooflijk eenvoudig om documentverwerkingstaken te beheren en te automatiseren. Probeer het eens en kijk hoe het uw workflow kan stroomlijnen.

## Veelgestelde vragen

### Kan ik het uiterlijk van de handtekeningregel aanpassen?
Absoluut! U kunt verschillende opties aanpassen in het`SignatureLineOptions` om aan uw behoeften te voldoen.

### Wat moet ik doen als ik geen PFX-certificaat heb?
U moet er een aanvragen bij een vertrouwde certificeringsinstantie. Het is essentieel voor het digitaal ondertekenen van documenten.

### Kan ik meerdere handtekeningregels aan een document toevoegen?
Ja, u kunt zoveel handtekeningregels toevoegen als nodig is door het invoegproces met verschillende opties te herhalen.

### Is Aspose.Words voor .NET compatibel met .NET Core?
Ja, Aspose.Words voor .NET ondersteunt .NET Core, waardoor het veelzijdig is voor verschillende ontwikkelomgevingen.

### Hoe veilig zijn de digitale handtekeningen?
Digitale handtekeningen gemaakt met Aspose.Words zijn zeer veilig, op voorwaarde dat u een geldig en vertrouwd certificaat gebruikt.