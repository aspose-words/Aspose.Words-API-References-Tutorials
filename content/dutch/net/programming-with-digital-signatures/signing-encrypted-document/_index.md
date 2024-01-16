---
title: Gecodeerd Word-document ondertekenen
linktitle: Gecodeerd Word-document ondertekenen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een gecodeerd Word-document digitaal kunt ondertekenen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/signing-encrypted-document/
---
In deze zelfstudie begeleiden we u bij de stappen voor het gebruik van de functie voor het ondertekenen van een gecodeerd Word-document met Aspose.Words voor .NET. Met deze functie kunt u een Word-document digitaal ondertekenen dat is gecodeerd met een decoderingswachtwoord. Volg onderstaande stappen:

## Stap 1: Handtekeningopties instellen

Maak een exemplaar van de klasse SignOptions en stel het decoderingswachtwoord in:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Zorg ervoor dat u het juiste decoderingswachtwoord voor uw gecodeerde document opgeeft.

## Stap 2: Het certificaat laden

Begin met het laden van het handtekeningcertificaat met behulp van de klasse CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Zorg ervoor dat u het juiste pad naar uw certificaat en het bijbehorende wachtwoord opgeeft.

## Stap 3: Het gecodeerde document ondertekenen

Gebruik de klasse DigitalSignatureUtil om het gecodeerde document te ondertekenen:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Zorg ervoor dat u de juiste paden opgeeft voor het gecodeerde document, het ondertekende document en het certificaat.

### Voorbeeldbroncode voor het ondertekenen van gecodeerde documenten met Aspose.Words voor .NET

Hier is de volledige broncode om een gecodeerd document te ondertekenen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Door deze stappen te volgen, kunt u eenvoudig een gecodeerd Word-document ondertekenen met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we het proces van het ondertekenen van een gecodeerd Word-document onderzocht met Aspose.Words voor .NET. Door het decoderingswachtwoord en het ondertekeningscertificaat op te geven, kunnen we een digitale handtekening aan een gecodeerd document toevoegen. Het ondertekenen van gecodeerde documenten waarborgt de authenticiteit en integriteit ervan en biedt een extra beveiligingslaag. Met Aspose.Words voor .NET kunt u gecodeerde documenten ondertekenen en de veiligheid en betrouwbaarheid van uw Word-bestanden behouden.

### Veelgestelde vragen

#### Vraag: Wat is documentondertekening in Aspose.Words voor .NET?

A: Documentondertekening in Aspose.Words voor .NET verwijst naar het proces van het digitaal ondertekenen van een Word-document om de authenticiteit, integriteit en onweerlegbaarheid ervan te garanderen. Het gaat om het toevoegen van een digitale handtekening aan het document met behulp van een certificaat.

#### Vraag: Wat is een gecodeerd Word-document?

A: Een gecodeerd Word-document is een document dat is gecodeerd met een wachtwoord. Versleuteling is een beveiligingsmaatregel die de inhoud van het document beschermt door het te versleutelen en onleesbaar te maken zonder het juiste decoderingswachtwoord.

#### Vraag: Hoe kan ik een gecodeerd Word-document ondertekenen met Aspose.Words voor .NET?

A: Om een gecodeerd Word-document te ondertekenen met Aspose.Words voor .NET, moet u het decoderingswachtwoord samen met het ondertekeningscertificaat opgeven. Volg deze stappen:
1.  Stel het decoderingswachtwoord in in het`SignOptions` voorwerp.
2.  Laad het ondertekeningscertificaat met behulp van de`CertificateHolder` klas.
3.  Gebruik de`DigitalSignatureUtil.Sign` methode om het gecodeerde document te ondertekenen, waarbij de noodzakelijke parameters worden opgegeven.

#### Vraag: Wat is het doel van het ondertekenen van een gecodeerd document?

A: Door een gecodeerd document te ondertekenen met Aspose.Words voor .NET kunt u een digitale handtekening aan het document toevoegen, zelfs als het gecodeerd is. Dit biedt een extra beveiligingslaag en garandeert de authenticiteit en integriteit van de gecodeerde inhoud. Hiermee kunnen ontvangers de herkomst van het document verifiëren en eventuele manipulatie detecteren.

#### Vraag: Kan ik een gecodeerd document ondertekenen zonder het decoderingswachtwoord op te geven?

A: Nee, om een gecodeerd document te ondertekenen, moet u het juiste decoderingswachtwoord opgeven. Het decoderingswachtwoord is vereist om toegang te krijgen tot de gecodeerde inhoud van het document en deze te wijzigen voordat de digitale handtekening wordt toegepast.

#### Vraag: Kan ik een gecodeerd Word-document ondertekenen met elk certificaat?

A: Om een gecodeerd Word-document te ondertekenen met Aspose.Words voor .NET, hebt u een geldig X.509-certificaat nodig. Het certificaat kan worden verkregen bij een vertrouwde certificeringsinstantie (CA) of een zelfondertekend certificaat kan worden gebruikt voor testdoeleinden.

#### Vraag: Kan ik meerdere gecodeerde Word-documenten ondertekenen met hetzelfde certificaat?

 A: Ja, u kunt meerdere gecodeerde Word-documenten ondertekenen met hetzelfde certificaat. Nadat u het certificaat hebt geladen met behulp van de`CertificateHolder` class, kunt u deze opnieuw gebruiken om meerdere gecodeerde documenten te ondertekenen.

#### Vraag: Kan ik de digitale handtekening van een ondertekend, gecodeerd document verifiëren?

 A: Ja, Aspose.Words voor .NET biedt functionaliteit om de digitale handtekening van een ondertekend gecodeerd document te verifiëren. U kunt gebruik maken van de`DigitalSignatureUtil.Verify` methode om de geldigheid en authenticiteit van de digitale handtekening te controleren.

#### Vraag: Welk bestandsformaat ondersteunt Aspose.Words voor .NET voor het ondertekenen van gecodeerde documenten?

 A: Aspose.Words voor .NET ondersteunt het ondertekenen van gecodeerde Word-documenten in het DOCX-bestandsformaat. U kunt gecodeerde DOCX-bestanden ondertekenen met behulp van de`DigitalSignatureUtil.Sign` methode samen met het benodigde decoderingswachtwoord en certificaat.

#### Vraag: Welke invloed heeft het ondertekenen van een gecodeerd document op de codering?

A: Het ondertekenen van een gecodeerd document met Aspose.Words voor .NET heeft geen invloed op de codering van het document. De codering blijft intact en de digitale handtekening wordt aan de gecodeerde inhoud toegevoegd. De digitale handtekening biedt extra beveiliging en verificatie zonder de op het document toegepaste codering in gevaar te brengen.