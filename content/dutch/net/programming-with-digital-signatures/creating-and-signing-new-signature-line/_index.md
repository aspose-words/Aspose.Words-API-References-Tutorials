---
title: Nieuwe handtekeningregel maken en ondertekenen
linktitle: Nieuwe handtekeningregel maken en ondertekenen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een nieuwe handtekeningregel in een Word-document kunt maken en ondertekenen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
In deze zelfstudie leiden we u door de stappen om de functie voor het maken en ondertekenen van een nieuwe handtekeningregel te gebruiken met Aspose.Words voor .NET. Met deze functie kunt u een handtekeningregel in een Word-document invoegen, aangepaste opties instellen en het document ondertekenen. Volg onderstaande stappen:

## Stap 1: Het document en de generator maken

Begin met het maken van een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: De handtekeningregel invoegen

Gebruik de methode InsertSignatureLine() van het DocumentBuilder-object om een nieuwe handtekeningregel in het document in te voegen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Stap 3: Sla het document op

Sla het gewijzigde document op:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft om het document op te slaan.

## Stap 4: Het document ondertekenen

Om het document te ondertekenen, moet u de handtekeningopties instellen en de klasse DigitalSignatureUtil gebruiken:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Zorg ervoor dat u de juiste paden opgeeft voor het document, de handtekeningregelafbeelding en het ondertekende document.

### Voorbeeldbroncode voor het maken en ondertekenen van een nieuwe handtekeningregel met Aspose.Words voor .NET

Hier is de volledige broncode om een nieuwe handtekeningregel te maken en te ondertekenen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Door deze stappen te volgen, kunt u eenvoudig een nieuwe handtekeningregel in uw Word-document maken en ondertekenen met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een nieuwe handtekeningregel in een Word-document kunt maken en ondertekenen met Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u eenvoudig een handtekeningregel in uw document invoegen, de opties ervan aanpassen en het document ondertekenen met een digitaal certificaat. Door handtekeningregels en digitale handtekeningen aan uw documenten toe te voegen, wordt de authenticiteit en integriteit ervan vergroot, waardoor ze veiliger en betrouwbaarder worden. Aspose.Words voor .NET biedt een krachtige API voor woordverwerking met handtekeningen en digitale certificaten in Word-documenten, waardoor u het ondertekeningsproces kunt automatiseren en de geldigheid van uw documenten kunt garanderen.

### Veelgestelde vragen

#### Vraag: Wat is een handtekeningregel in een Word-document?

A: Een handtekeningregel in een Word-document is een tijdelijke aanduiding die aangeeft waar een handtekening moet worden geplaatst. Het bevat doorgaans de naam, titel en datum en biedt ruimte voor een handgeschreven of digitale handtekening.

#### Vraag: Hoe kan ik een handtekeningregel in een Word-document maken met Aspose.Words voor .NET?

A: Om een handtekeningregel in een Word-document te maken met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Maak een exemplaar van de`Document` klasse en een`DocumentBuilder` voorwerp.
2.  Gebruik de`InsertSignatureLine` werkwijze van de`DocumentBuilder` object om een nieuwe handtekeningregel in het document in te voegen.
3. Sla het gewijzigde document op.

#### Vraag: Kan ik de opties voor de handtekeningregel aanpassen, zoals naam, titel en datum?

 A: Ja, u kunt de opties voor de handtekeningregel aanpassen. De`SignatureLineOptions` class biedt eigenschappen om de gewenste opties in te stellen, zoals`Signer`, `SignerTitle`, `ShowDate`, enz. U kunt deze eigenschappen wijzigen voordat u de handtekeningregel invoegt.

#### Vraag: Hoe kan ik het document ondertekenen nadat ik een handtekeningregel heb aangemaakt?

 A: Om het document te ondertekenen nadat u een handtekeningregel hebt gemaakt, moet u de handtekeningopties instellen en de`DigitalSignatureUtil` klas. Hier zijn de stappen:
1.  Stel de`SignatureLineId` eigendom in de`SignOptions` bezwaar maken tegen de ID van de handtekeningregel.
2.  Stel de`SignatureLineImage` eigendom in de`SignOptions` bezwaar maken tegen de afbeelding van de handtekening die u wilt gebruiken.
3.  Laad het ondertekeningscertificaat met behulp van de`CertificateHolder` klas.
4.  Gebruik de`DigitalSignatureUtil.Sign` methode om het document te ondertekenen, waarbij de nodige parameters worden opgegeven.

#### Vraag: Kan ik een afbeelding van een digitale handtekening gebruiken om het document te ondertekenen?

 A: Ja, u kunt een afbeelding van een digitale handtekening gebruiken om het document te ondertekenen. Om dit te doen, moet u het afbeeldingsbestand in de`SignOptions` object met behulp van de`SignatureLineImage`eigendom. De afbeelding kan elk ondersteund afbeeldingsformaat hebben, zoals JPEG, PNG of EMF.

#### Vraag: Wat is het doel van het maken en ondertekenen van een nieuwe handtekeningregel in een Word-document?

A: Door een nieuwe handtekeningregel in een Word-document te maken en te ondertekenen met Aspose.Words voor .NET kunt u een tijdelijke aanduiding voor een handtekening toevoegen en het document vervolgens ondertekenen met een digitaal certificaat. Dit proces garandeert de authenticiteit en integriteit van het document en levert het bewijs van goedkeuring of overeenstemming.

#### Vraag: Kan ik meerdere handtekeningregels in een Word-document maken en ondertekenen met Aspose.Words voor .NET?

A: Ja, u kunt meerdere handtekeningregels in een Word-document maken en ondertekenen met Aspose.Words voor .NET. Elke handtekeningregel kan zijn eigen unieke ID en opties hebben. U kunt de stappen herhalen om extra handtekeningregels in het document te maken en te ondertekenen.

#### Vraag: Kan ik de handtekeningregel wijzigen of aanvullende informatie toevoegen nadat deze is ondertekend?

A: Zodra een handtekeningregel is ondertekend, wordt deze onderdeel van de inhoud van het document en kan deze niet afzonderlijk worden gewijzigd. U kunt echter aanvullende informatie of inhoud toevoegen na de ondertekende handtekeningregel.

#### Vraag: Kan ik de digitale handtekening verifiëren van een document dat een handtekeningregel bevat?

 A: Ja, Aspose.Words voor .NET biedt functionaliteit om de digitale handtekening te verifiëren van een document dat een handtekeningregel bevat. U kunt gebruik maken van de`DigitalSignatureUtil.Verify` methode om de geldigheid en authenticiteit van de digitale handtekening te controleren.

#### Vraag: Welk bestandsformaat ondersteunt Aspose.Words voor .NET voor het maken en ondertekenen van handtekeningregels?

A: Aspose.Words voor .NET ondersteunt het maken en ondertekenen van handtekeningregels in het DOCX-bestandsformaat. U kunt handtekeningregels in DOCX-bestanden maken en ondertekenen met behulp van de meegeleverde methoden en klassen.