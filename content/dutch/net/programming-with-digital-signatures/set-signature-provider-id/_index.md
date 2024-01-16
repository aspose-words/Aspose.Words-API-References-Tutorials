---
title: Stel de handtekeningprovider-ID in in een Word-document
linktitle: Stel de handtekeningprovider-ID in in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de handtekeningprovider-ID in een Word-document instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/set-signature-provider-id/
---
In deze zelfstudie leiden we u door de stappen om de functie Set Signature Provider ID te gebruiken met Aspose.Words voor .NET. Met deze functie kunt u de handtekeningprovider-ID opgeven voor een handtekeningregel in een Word-document. Volg onderstaande stappen:

## Stap 1: Het document laden en toegang krijgen tot de handtekeningregel

Begin met het uploaden van het document met de handtekeningregel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Stap 2: Handtekeningopties instellen

Maak een exemplaar van de klasse SignOptions en stel de ondertekeningsopties in, inclusief de provider-ID:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Stap 3: Het document ondertekenen

Om het document te ondertekenen, moet u de klasse DigitalSignatureUtil gebruiken en het ondertekeningscertificaat opgeven:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Zorg ervoor dat u de juiste paden opgeeft voor het document, het certificaat en het ondertekende document.

### Voorbeeldbroncode voor Set Signature Provider Id met Aspose.Words voor .NET

Hier is de volledige broncode om de ID van de handtekeningprovider in te stellen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Maak de Signature Provider ID in uw Word-document af met Aspose.Words voor .NET.


## Conclusie

In deze zelfstudie hebben we geleerd hoe u de handtekeningprovider-ID voor een handtekeningregel in een Word-document kunt instellen met behulp van Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u eenvoudig het document laden, toegang krijgen tot de handtekeningregel, de provider-ID instellen en het document ondertekenen. De mogelijkheid om de ID van de handtekeningprovider in te stellen helpt de identiteit en betrouwbaarheid van de ondertekenaar vast te stellen, waardoor de veiligheid en integriteit van uw Word-documenten wordt verbeterd. Aspose.Words voor .NET biedt een robuuste API voor woordverwerking met digitale handtekeningen, waardoor u het handtekeningproces eenvoudig kunt aanpassen en beheren.

### Veelgestelde vragen over het instellen van de ID van de handtekeningprovider in een Word-document

#### Vraag: Wat is een handtekeningprovider-ID in een Word-document?

A: Een handtekeningaanbieder-ID in een Word-document is een unieke identificatie die de aanbieder van een digitale handtekening specificeert. Het helpt bij het identificeren van de entiteit of organisatie die verantwoordelijk is voor het maken en beheren van de digitale handtekening.

#### Vraag: Hoe kan ik de handtekeningprovider-ID instellen voor een handtekeningregel in een Word-document met Aspose.Words voor .NET?

A: Om de handtekeningprovider-ID in te stellen voor een handtekeningregel in een Word-document met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Laad het document met behulp van de`Document` class en geef het pad naar het documentbestand op.
2.  Krijg toegang tot de handtekeningregel met behulp van de juiste methode of eigenschap. U kunt bijvoorbeeld gebruiken`GetChild` methode om de vorm van de handtekeninglijn op te halen.
3. Haal de provider-ID op uit de handtekeningregel.
4.  Maak een exemplaar van de`SignOptions` klasse en stel de`ProviderId` eigenschap aan de opgehaalde provider-ID.
5.  Gebruik de`DigitalSignatureUtil.Sign` methode om het document te ondertekenen, waarbij de nodige parameters worden opgegeven, waaronder de`SignOptions` voorwerp.

#### Vraag: Hoe krijg ik toegang tot de handtekeningregel in een Word-document met Aspose.Words voor .NET?

 A: Om toegang te krijgen tot de handtekeninglijn in een Word-document met Aspose.Words voor .NET, kunt u de juiste methode of eigenschap gebruiken om de vorm van de handtekeninglijn op te halen uit de structuur van het document. U kunt bijvoorbeeld gebruik maken van de`GetChild` methode met de juiste parameters om de gewenste handtekeninglijnvorm te verkrijgen.

#### Vraag: Kan ik de ID van de handtekeningprovider instellen voor meerdere handtekeningregels in een Word-document?

 A: Ja, u kunt de ID van de handtekeningprovider instellen voor meerdere handtekeningregels in een Word-document. U kunt de verzameling handtekeningregels in het document doorlopen en de provider-ID voor elke handtekeningregel afzonderlijk instellen met behulp van de`SignOptions.ProviderId` eigendom.

#### Vraag: Wat is het doel van de handtekeningprovider-ID in een Word-document?

A: De ID van de handtekeningprovider in een Word-document dient ter identificatie van de entiteit of organisatie die verantwoordelijk is voor het maken en beheren van de digitale handtekening. Het helpt de authenticiteit en betrouwbaarheid van de digitale handtekening vast te stellen door deze aan een specifieke provider te koppelen.

#### Vraag: Welk type digitale certificaten kan worden gebruikt voor het instellen van de ID van de handtekeningprovider in een Word-document?

A: U kunt digitale X.509-certificaten met de juiste providerinformatie gebruiken om de ID van de handtekeningprovider in een Word-document in te stellen. Het digitale certificaat moet zijn uitgegeven door een vertrouwde certificeringsinstantie (CA) en de benodigde metagegevens bevatten om de aanbieder te identificeren.