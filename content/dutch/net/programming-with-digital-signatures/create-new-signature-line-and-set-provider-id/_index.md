---
title: Maak een nieuwe handtekeningregel en stel de provider-ID in
linktitle: Maak een nieuwe handtekeningregel en stel de provider-ID in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een nieuwe handtekeningregel maakt en de provider-ID in een Word-document instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
In deze zelfstudie leiden we u door de stappen om de functie Nieuwe handtekeningregel maken en Provider-ID instellen te gebruiken met Aspose.Words voor .NET. Met deze functie kunt u een handtekeningregel in een Word-document invoegen, aangepaste opties instellen en het document ondertekenen. Volg onderstaande stappen:

## Stap 1: Het document en de generator maken

Begin met het maken van een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Handtekeninglijnopties instellen

Maak een exemplaar van de klasse SignatureLineOptions en stel de gewenste opties in:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Stap 3: De handtekeningregel invoegen

Gebruik de methode InsertSignatureLine() van het DocumentBuilder-object om de handtekeningregel in het document in te voegen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Stap 4: Stel de provider-ID in

Stel de provider-ID voor de handtekeningregel in met behulp van de eigenschap ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Zorg ervoor dat u de juiste provider-ID voor uw gebruiksscenario opgeeft.

## Stap 5: Bewaar het document

Sla het gewijzigde document op:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het document op te slaan.

## Stap 6: Het document ondertekenen

Om het document te ondertekenen, moet u de handtekeningopties instellen en de klasse DigitalSignatureUtil gebruiken:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Zorg ervoor dat u de juiste paden opgeeft voor het document, het certificaat en het ondertekende document.

### Voorbeeldbroncode voor het maken van een nieuwe handtekeningregel en het instellen van de provider-ID met behulp van Aspose.Words voor .NET

Hier is de volledige broncode om een nieuwe handtekeningregel te maken en de provider-ID in te stellen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

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

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Door deze stappen te volgen, kunt u eenvoudig een nieuwe handtekeningregel maken en de provider-ID in uw Word-document instellen met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we de functie onderzocht van het maken van een nieuwe handtekeningregel en het instellen van de provider-ID in een Word-document met behulp van Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u eenvoudig een handtekeningregel met aangepaste opties invoegen en deze aan een specifieke provider koppelen met behulp van de provider-ID. Door handtekeningregels toe te voegen en de providerinformatie aan te passen, wordt de authenticiteit en betrouwbaarheid van uw documenten vergroot. Aspose.Words voor .NET biedt een krachtige API voor woordenverwerking met handtekeningregels en digitale certificaten in Word-documenten, waardoor u het ondertekeningsproces kunt automatiseren en de geldigheid van uw documenten kunt garanderen.

### Veelgestelde vragen

#### Vraag: Wat is een provider-ID in een handtekeningregel?

A: Een provider-ID in een handtekeningregel is een unieke identificatie die de aanbieder van de digitale handtekening vertegenwoordigt. Het helpt bij het identificeren van de bron of organisatie die verantwoordelijk is voor de handtekening.

#### Vraag: Hoe kan ik een nieuwe handtekeningregel in een Word-document maken met Aspose.Words voor .NET?

A: Om een nieuwe handtekeningregel in een Word-document te maken met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp.
2.  Maak een exemplaar van de`SignatureLineOptions` class en stel de gewenste handtekeninglijnopties in.
3.  Gebruik de`InsertSignatureLine` werkwijze van de`DocumentBuilder` object om de handtekeningregel in het document in te voegen.

#### Vraag: Kan ik de opties van de handtekeningregel aanpassen, zoals de naam, titel en instructies van de ondertekenaar?

 A: Ja, u kunt de opties van de handtekeningregel aanpassen. De`SignatureLineOptions` class biedt eigenschappen om de gewenste opties in te stellen, zoals`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, enz. U kunt deze eigenschappen wijzigen voordat u de handtekeningregel invoegt.

#### Vraag: Wat is het doel van het instellen van de provider-ID voor een handtekeningregel?

A: Door het provider-ID voor een handtekeningregel in te stellen, kunt u de bron of organisatie identificeren die verantwoordelijk is voor de digitale handtekening. Hiermee kunt u de handtekening koppelen aan een specifieke aanbieder of entiteit, waardoor aanvullende informatie wordt verstrekt over de herkomst en betrouwbaarheid van de handtekening.

#### Vraag: Hoe kan ik de provider-ID voor een handtekeningregel instellen met Aspose.Words voor .NET?

A: Om de provider-ID voor een handtekeningregel in te stellen met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Nadat u de handtekeningregel hebt ingevoegd, gaat u naar het`ProviderId` eigendom van de`SignatureLine` voorwerp.
2.  Stel de`ProviderId` eigenschap naar de gewenste provider-ID-waarde met behulp van de`Guid` data type.

#### Vraag: Kan ik het document ondertekenen nadat ik een nieuwe handtekeningregel heb aangemaakt en de provider-ID heb ingesteld?

 A: Ja, nadat u een nieuwe handtekeningregel heeft aangemaakt en de provider-ID heeft ingesteld, kunt u het document ondertekenen. Om het document te ondertekenen, moet u de handtekeningopties instellen, waaronder de handtekeningregel-ID, provider-ID, opmerkingen en ondertekeningstijd. Gebruik dan de`DigitalSignatureUtil.Sign` methode om het document te ondertekenen met een digitaal certificaat.

#### Vraag: Kan ik een specifieke provider-ID opgeven voor elke handtekeningregel in een Word-document?

A: Ja, u kunt voor elke handtekeningregel in een Word-document een specifieke provider-ID opgeven. Nadat u elke handtekeningregel hebt ingevoegd, kunt u de provider-ID voor die specifieke handtekeningregel instellen door naar de`ProviderId` eigendom van de betreffende`SignatureLine` voorwerp.

#### Vraag: Hoe kan ik het gewijzigde document opslaan nadat ik een nieuwe handtekeningregel heb aangemaakt en de provider-ID heb ingesteld?

 A: Om het gewijzigde document op te slaan na het aanmaken van een nieuwe handtekeningregel en het instellen van de provider-ID, kunt u de`Save` werkwijze van de`Document` voorwerp. Geef het juiste pad en de juiste bestandsnaam op om het document op te slaan.

#### Vraag: Welk bestandsformaat ondersteunt Aspose.Words voor .NET voor het maken en ondertekenen van handtekeningregels?

A: Aspose.Words voor .NET ondersteunt het maken en ondertekenen van handtekeningregels in het DOCX-bestandsformaat. U kunt handtekeningregels in DOCX-bestanden maken en ondertekenen met behulp van de meegeleverde methoden en klassen.

#### Vraag: Kan ik de provider-ID of andere opties van een handtekeningregel wijzigen nadat deze is ondertekend?

A: Zodra een handtekeningregel is ondertekend, wordt deze onderdeel van de inhoud van het document en kan deze niet afzonderlijk worden gewijzigd. Voor elke wijziging aan de handtekeningregel, zoals het wijzigen van de provider-ID of andere opties, moet de bestaande handtekening worden verwijderd en moet een nieuwe handtekeningregel worden gemaakt.