---
title: Onderteken Word-document
linktitle: Onderteken Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een Word-document digitaal kunt ondertekenen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/sign-document/
---
In deze zelfstudie leiden we u door de stappen om de functie voor documentondertekening te gebruiken met Aspose.Words voor .NET. Met deze functie kunt u een Word-document digitaal ondertekenen met behulp van een certificaat. Volg onderstaande stappen:

## Stap 1: Het certificaat laden

Begin met het laden van het handtekeningcertificaat met behulp van de klasse CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Zorg ervoor dat u het juiste pad naar uw certificaat en het bijbehorende wachtwoord opgeeft.

## Stap 2: Het document ondertekenen

Gebruik de klasse DigitalSignatureUtil om het document te ondertekenen:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Zorg ervoor dat u de juiste paden voor het brondocument en het ondertekende document opgeeft.

### Voorbeeldbroncode voor Sign Document met Aspose.Words voor .NET

Hier is de volledige broncode om een document te ondertekenen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Door deze stappen te volgen, kunt u eenvoudig een Word-document ondertekenen met Aspose.Words voor .NET.

## Conclusie

 In deze zelfstudie hebben we de functie voor documentondertekening in Aspose.Words voor .NET onderzocht. Door een handtekeningcertificaat te laden en de`DigitalSignatureUtil.Sign` methode kunnen we een Word-document digitaal ondertekenen. Het ondertekenen van documenten biedt authenticatie en waarborgt de integriteit van de inhoud van het document, waardoor het een waardevolle functie is voor veilig en betrouwbaar documentbeheer.

### Veelgestelde vragen over het gebarenwoorddocument

#### Vraag: Wat is documentondertekening in Aspose.Words voor .NET?

A: Documentondertekening in Aspose.Words voor .NET verwijst naar het proces van het digitaal ondertekenen van een Word-document met behulp van een certificaat. Deze functie voegt een digitale handtekening toe aan het document, waardoor authenticiteit, integriteit en onweerlegbaarheid van de inhoud van het document wordt geboden.

#### Vraag: Hoe kan ik het handtekeningcertificaat in Aspose.Words voor .NET laden?

 A: Om het handtekeningcertificaat in Aspose.Words voor .NET te laden, kunt u de`CertificateHolder` klas. Maak een exemplaar van`CertificateHolder` door het pad naar het certificaatbestand en het bijbehorende wachtwoord op te geven. Hier is een voorbeeld:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Zorg ervoor dat u het juiste pad naar uw certificaat en het bijbehorende wachtwoord opgeeft.

#### Vraag: Hoe onderteken ik een Word-document met Aspose.Words voor .NET?

 A: Om een Word-document te ondertekenen met Aspose.Words voor .NET, kunt u de`DigitalSignatureUtil` klas. Bel de`Sign` methode, waarbij het pad naar het brondocument, het pad naar het ondertekende document (uitvoer) en de`CertificateHolder` voorwerp. Hier is een voorbeeld:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Zorg ervoor dat u de juiste paden opgeeft voor het brondocument en het ondertekende document (uitvoer).

#### Vraag: Wat is het doel van het ondertekenen van documenten?

A: Het ondertekenen van documenten dient als een methode om de authenticiteit en integriteit van een document te garanderen. Door een document digitaal te ondertekenen, kunt u de herkomst ervan bewijzen, verifiëren dat de inhoud niet is gewijzigd en onweerlegbaarheid garanderen. Het ondertekenen van documenten wordt vaak gebruikt voor juridische, financiële en gevoelige documenten.

#### Vraag: Kan ik elk certificaat gebruiken voor het ondertekenen van documenten in Aspose.Words voor .NET?

A: Voor het ondertekenen van documenten in Aspose.Words voor .NET moet u een geldig X.509-certificaat gebruiken. Dit certificaat kan worden verkregen bij een vertrouwde certificeringsinstantie (CA) of een zelfondertekend certificaat kan worden gebruikt voor testdoeleinden.

#### Vraag: Welk bestandsformaat ondersteunt Aspose.Words voor .NET voor het ondertekenen van documenten?

 A: Aspose.Words voor .NET ondersteunt documentondertekening voor Word-documenten in het DOCX-bestandsformaat. U kunt DOCX-bestanden ondertekenen met behulp van de`DigitalSignatureUtil` klasse en het bijbehorende certificaat.

#### Vraag: Kan ik meerdere Word-documenten ondertekenen met hetzelfde certificaat?

A: Ja, u kunt meerdere Word-documenten ondertekenen met hetzelfde certificaat. Nadat u het certificaat hebt geladen met behulp van de`CertificateHolder` class, kunt u deze opnieuw gebruiken om meerdere documenten te ondertekenen door de`DigitalSignatureUtil.Sign` methode met verschillende bron- en ondertekende documentpaden.

#### Vraag: Wijzigt het ondertekenen van documenten het originele document?

A: Het ondertekenen van documenten met Aspose.Words voor .NET wijzigt het originele document niet. In plaats daarvan wordt er een digitaal ondertekende kopie van het document gemaakt, waarbij het originele document intact blijft. De digitaal ondertekende kopie bevat de toegevoegde digitale handtekening, waardoor de integriteit van de inhoud van het document wordt gewaarborgd.

#### Vraag: Kan ik de digitale handtekening van een ondertekend document verifiëren met Aspose.Words voor .NET?

 A: Ja, Aspose.Words voor .NET biedt functionaliteit om de digitale handtekening van een ondertekend document te verifiëren. U kunt gebruik maken van de`DigitalSignatureUtil.Verify` methode om de geldigheid en authenticiteit van de digitale handtekening te controleren.