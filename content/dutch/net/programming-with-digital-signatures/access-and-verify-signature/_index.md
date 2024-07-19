---
title: Toegang tot en verifieer de handtekening in een Word-document
linktitle: Toegang tot en verifieer de handtekening in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Krijg toegang tot en verifieer digitale handtekeningen in Word-documenten met Aspose.Words voor .NET met deze uitgebreide stapsgewijze handleiding. Garandeer moeiteloos de authenticiteit van documenten.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/access-and-verify-signature/
---
## Invoering

Hallo daar, mede-technologieliefhebbers! Bent u ooit in een situatie terechtgekomen waarin u digitale handtekeningen in een Word-document moest openen en verifiëren, maar geen idee had waar u moest beginnen? Nou, je hebt geluk! Vandaag duiken we in de wondere wereld van Aspose.Words voor .NET, een krachtige bibliotheek die het verwerken van Word-documenten een fluitje van een cent maakt. We leiden u stap voor stap door het proces, zodat u aan het einde van deze handleiding een professional bent in het verifiëren van digitale handtekeningen in Word-documenten. Laten we beginnen!

## Vereisten

Voordat we ingaan op de details, zijn er een paar dingen die je moet regelen:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw computer is geïnstalleerd. Dit is waar u uw code schrijft en uitvoert.
2.  Aspose.Words voor .NET: Aspose.Words voor .NET moet geïnstalleerd zijn. Je kunt het downloaden[hier](https://releases.aspose.com/words/net/) . Vergeet niet uw gratis proefperiode aan te vragen[hier](https://releases.aspose.com/) als je dat nog niet hebt gedaan!
3. Een digitaal ondertekend Word-document: zorg dat u een Word-document hebt dat al digitaal is ondertekend. Dit is het bestand waarmee u gaat werken om de handtekeningen te verifiëren.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Met deze naamruimten kunt u de Aspose.Words-functies in uw project gebruiken.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.DigitalSignatures;
```

Oké, laten we dit opsplitsen in beheersbare stappen. Elke stap begeleidt u door een specifiek deel van het proces. Klaar? Laten we gaan!

## Stap 1: Stel uw project in

Voordat u een digitale handtekening kunt verifiëren, moet u uw project instellen in Visual Studio. Hier is hoe:

### Maak een nieuw project

1. Open Visuele Studio.
2. Klik op Een nieuw project aanmaken.
3. Selecteer Console-app (.NET Core) of Console-app (.NET Framework), afhankelijk van uw voorkeur.
4. Klik op Volgende, geef uw project een naam en klik op Maken.

### Installeer Aspose.Words voor .NET

1. Klik in de Solution Explorer met de rechtermuisknop op uw projectnaam en selecteer NuGet-pakketten beheren.
2. Zoek in NuGet Package Manager naar Aspose.Words.
3. Klik op Installeren om het aan uw project toe te voegen.

## Stap 2: Laad het digitaal ondertekende Word-document

Nu uw project is ingesteld, gaan we het Word-document laden dat digitaal is ondertekend.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap. Dit codefragment initialiseert een nieuw`Document` object en laadt uw ondertekende Word-document.

## Stap 3: Toegang tot de digitale handtekeningen

Nu uw document is geladen, is het tijd om toegang te krijgen tot de digitale handtekeningen.

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine("* Signature Found *");
    Console.WriteLine("Is valid: " + signature.IsValid);
    Console.WriteLine("Reason for signing: " + signature.Comments); 
    Console.WriteLine("Time of signing: " + signature.SignTime);
    Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
    Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
    Console.WriteLine();
}
```

Deze code loopt door elke digitale handtekening in het document en drukt verschillende details over de handtekening af. Laten we eens opsplitsen wat elk onderdeel doet:

1. Handtekening gevonden: Geeft aan dat er een handtekening is gevonden.
2. Is geldig: Controleert of de handtekening geldig is.
3. Reden voor ondertekening: Toont de reden voor ondertekening, indien beschikbaar.
4. Tijdstip van ondertekening: toont de tijdstempel van het moment waarop het document is ondertekend.
5. Onderwerpnaam: Haalt de onderwerpnaam op uit het certificaat.
6. Naam uitgever: Haalt de naam van de uitgever op uit het certificaat.

## Stap 4: Voer uw code uit

Nu alles is ingesteld, is het tijd om uw code uit te voeren en de resultaten te bekijken.


1. Druk op F5 of klik op de Start-knop in Visual Studio om uw programma uit te voeren.
2. Als uw document digitaal is ondertekend, ziet u de handtekeninggegevens in de console.

## Stap 5: Potentiële fouten aanpakken

Het is altijd een goed idee om eventuele fouten die zich kunnen voordoen, af te handelen. Laten we wat basisfoutafhandeling aan onze code toevoegen.

```csharp
try
{
    // Het pad naar de documentenmap.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
    Document doc = new Document(dataDir + "Digitally signed.docx");

    foreach (DigitalSignature signature in doc.DigitalSignatures)
    {
        Console.WriteLine("* Signature Found *");
        Console.WriteLine("Is valid: " + signature.IsValid);
        Console.WriteLine("Reason for signing: " + signature.Comments); 
        Console.WriteLine("Time of signing: " + signature.SignTime);
        Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
        Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
        Console.WriteLine();
    }
}
catch (Exception ex)
{
    Console.WriteLine("An error occurred: " + ex.Message);
}
```

Hierdoor worden eventuele uitzonderingen opgespoord en wordt er een foutmelding afgedrukt.

## Conclusie

En daar heb je het! U hebt met succes digitale handtekeningen in een Word-document geopend en geverifieerd met Aspose.Words voor .NET. Het is niet zo intimiderend als het lijkt, toch? Met deze stappen kunt u vol vertrouwen omgaan met digitale handtekeningen in uw Word-documenten, waardoor de authenticiteit en integriteit ervan wordt gewaarborgd. Veel codeerplezier!

## Veelgestelde vragen

### Kan ik Aspose.Words voor .NET gebruiken om digitale handtekeningen aan een Word-document toe te voegen?

Ja, u kunt Aspose.Words voor .NET gebruiken om digitale handtekeningen aan Word-documenten toe te voegen. De bibliotheek biedt uitgebreide functies voor het toevoegen en verifiëren van digitale handtekeningen.

### Welke soorten digitale handtekeningen kan Aspose.Words voor .NET verifiëren?

Aspose.Words voor .NET kan digitale handtekeningen verifiëren in DOCX-bestanden die X.509-certificaten gebruiken.

### Is Aspose.Words voor .NET compatibel met alle versies van Microsoft Word?

Aspose.Words voor .NET ondersteunt alle versies van Microsoft Word-documenten, inclusief DOC, DOCX, RTF en meer.

### Hoe krijg ik een tijdelijke licentie voor Aspose.Words voor .NET?

 U kunt een tijdelijke licentie voor Aspose.Words voor .NET verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/). Hierdoor kunt u zonder enige beperking alle functies van de bibliotheek uitproberen.

### Waar kan ik meer documentatie vinden over Aspose.Words voor .NET?

 U kunt gedetailleerde documentatie vinden voor Aspose.Words voor .NET[hier](https://reference.aspose.com/words/net/).