---
title: Bestaande handtekeningregel in Word-document ondertekenen
linktitle: Bestaande handtekeningregel in Word-document ondertekenen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een bestaande handtekeningregel in een Word-document kunt ondertekenen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/signing-existing-signature-line/
---
In deze zelfstudie leiden we u door de stappen om de handtekeningfunctie van een bestaande handtekeningregel te gebruiken met Aspose.Words voor .NET. Met deze functie kunt u een handtekeningregel die al in een Word-document aanwezig is, digitaal ondertekenen. Volg onderstaande stappen:

## Stap 1: Het document laden en toegang krijgen tot de handtekeningregel

Begin met het uploaden van het document met de bestaande handtekeningregel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Stap 2: Handtekeningopties instellen

Maak een exemplaar van de klasse SignOptions en stel de handtekeningopties in, inclusief handtekeningregel-ID en handtekeningregelafbeelding:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Zorg ervoor dat u het juiste pad naar de handtekeninglijnafbeelding opgeeft.

## Stap 3: Het certificaat laden

Begin met het laden van het handtekeningcertificaat met behulp van de klasse CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Zorg ervoor dat u het juiste pad naar uw certificaat en het bijbehorende wachtwoord opgeeft.

## Stap 4: Ondertekening van de bestaande handtekeningregel

Gebruik de klasse DigitalSignatureUtil om de bestaande handtekeningregel te ondertekenen:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Zorg ervoor dat u de juiste paden opgeeft voor het brondocument, het ondertekende document en het certificaat.

### Voorbeeldbroncode voor het ondertekenen van bestaande handtekeningregels met Aspose.Words voor .NET

Hier is de volledige broncode om een bestaande handtekeningregel te ondertekenen met Aspose.Words voor .NET:


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Door deze stappen te volgen, kunt u eenvoudig een bestaande handtekeningregel in een Word-document ondertekenen met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een bestaande handtekeningregel in een Word-document kunt ondertekenen met Aspose.Words voor .NET. Door de gegeven stappen te volgen, kunt u het document eenvoudig laden, toegang krijgen tot de bestaande handtekeningregel, de ondertekeningsopties instellen en het document ondertekenen. De mogelijkheid om een bestaande handtekeningregel te ondertekenen biedt een handige manier om digitale handtekeningen toe te voegen aan vooraf gedefinieerde gebieden in uw Word-documenten, waardoor de documentintegriteit en authenticatie wordt gegarandeerd. Aspose.Words voor .NET biedt een krachtige API voor tekstverwerking met digitale handtekeningen, waarmee u het ondertekeningsproces kunt aanpassen en de beveiliging van uw Word-documenten kunt verbeteren.

### Veelgestelde vragen

#### Vraag: Wat is een bestaande handtekeningregel in een Word-document?

A: Een bestaande handtekeningregel in een Word-document is een vooraf gedefinieerd gebied waar een handtekening kan worden geplaatst. Het wordt doorgaans weergegeven door een vorm of object in het document en dient als een aangewezen ruimte voor de ondertekenaar om zijn digitale handtekening toe te voegen.

#### Vraag: Hoe kan ik een bestaande handtekeningregel in een Word-document ondertekenen met Aspose.Words voor .NET?

A: Om een bestaande handtekeningregel in een Word-document te ondertekenen met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Laad het document met behulp van de`Document` class en geef het pad naar het documentbestand op.
2.  Krijg toegang tot de bestaande handtekeningregel met behulp van de juiste methode of eigenschap. U kunt bijvoorbeeld gebruiken`GetChild` methode om de vorm van de handtekeninglijn op te halen.
3.  Maak een exemplaar van de`SignOptions` klasse en stel de`SignatureLineId` eigenschap toe aan de ID van de bestaande handtekeningregel.
4.  Stel de`SignatureLineImage` eigendom van de`SignOptions` klasse toe aan de afbeelding die de digitale handtekening vertegenwoordigt.
5.  Laad het ondertekeningscertificaat met behulp van de`CertificateHolder` class en geef het benodigde certificaat en wachtwoord op.
6.  Gebruik de`DigitalSignatureUtil.Sign` methode om het document te ondertekenen, waarbij de nodige parameters worden opgegeven, waaronder de`SignOptions` voorwerp.

#### Vraag: Hoe krijg ik toegang tot de bestaande handtekeningregel in een Word-document met Aspose.Words voor .NET?

 A: Om toegang te krijgen tot de bestaande handtekeninglijn in een Word-document met Aspose.Words voor .NET, kunt u de juiste methode of eigenschap gebruiken om de vorm van de handtekeninglijn uit de structuur van het document op te halen. U kunt bijvoorbeeld gebruik maken van de`GetChild` methode met de juiste parameters om de gewenste handtekeninglijnvorm te verkrijgen.

#### Vraag: Kan ik het uiterlijk van de digitale handtekening in een bestaande handtekeningregel aanpassen?

A: Ja, u kunt het uiterlijk van de digitale handtekening in een bestaande handtekeningregel aanpassen door een afbeeldingsbestand aan te bieden dat de handtekening vertegenwoordigt. De afbeelding kan een logo, een handgeschreven handtekening of een andere grafische weergave van de handtekening zijn. U kunt de`SignatureLineImage` eigendom van de`SignOptions` klasse toe aan de bytes van het afbeeldingsbestand.

#### Vraag: Kan ik meerdere bestaande handtekeningregels in een Word-document ondertekenen?
 A: Ja, u kunt meerdere bestaande handtekeningregels in een Word-document ondertekenen. U moet de stappen voor elke handtekeningregel afzonderlijk volgen en de juiste instelling instellen`SignatureLineId` En`SignatureLineImage` waarden in de`SignOptions` object voor elke handtekeningregel.

#### Vraag: Welk formaat moet het afbeeldingsbestand hebben voor de digitale handtekening in een bestaande handtekeningregel?

 A: Het afbeeldingsbestand voor de digitale handtekening in een bestaande handtekeningregel kan verschillende formaten hebben, zoals PNG, JPEG, BMP of GIF. U kunt het bestandspad opgeven of de bytes van het afbeeldingsbestand lezen en toewijzen aan de`SignatureLineImage` eigendom van de`SignOptions` klas.
