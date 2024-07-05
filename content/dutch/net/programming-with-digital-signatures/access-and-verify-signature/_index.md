---
title: Toegang tot en verifieer de handtekening in een Word-document
linktitle: Toegang tot en verifieer de handtekening in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u digitale handtekeningen in een Word-document kunt openen en verifiëren met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-digital-signatures/access-and-verify-signature/
---
In deze zelfstudie begeleiden we u bij de stappen voor het gebruik van de toegangs- en handtekeningverificatiefunctie van Aspose.Words voor .NET. Met deze functie hebt u toegang tot digitale handtekeningen in een Word-document en kunt u de geldigheid ervan verifiëren. Volg onderstaande stappen:

## Stap 1: Het document laden en toegang krijgen tot handtekeningen

Begin met het uploaden van het document met digitale handtekeningen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Stap 2: Blader door digitale handtekeningen

Gebruik een lus om alle digitale handtekeningen in het document te doorlopen:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Toegang tot handtekeninginformatie
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Deze eigenschap is alleen beschikbaar in MS Word-documenten.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Zorg ervoor dat u de displayberichten aanpast aan uw behoeften.

### Voorbeeldbroncode voor toegang en verificatie van handtekening met Aspose.Words voor .NET

Hier is de volledige broncode voor toegang en handtekeningverificatie met Aspose.Words voor .NET:

```csharp
	
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Deze eigenschap is alleen beschikbaar in MS Word-documenten.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Door deze stappen te volgen, kunt u eenvoudig de digitale handtekeningen in uw Word-document openen en verifiëren met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we de functie van het openen en verifiëren van digitale handtekeningen in een Word-document onderzocht met behulp van Aspose.Words voor .NET. Door de aangegeven stappen te volgen, kunt u eenvoudig een document laden, toegang krijgen tot de digitale handtekeningen en de geldigheid ervan verifiëren. De mogelijkheid om digitale handtekeningen te openen en te verifiëren biedt een manier om de integriteit en authenticiteit van uw Word-documenten te garanderen. Aspose.Words voor .NET biedt een krachtige API voor woordverwerking met digitale handtekeningen, waarmee u het verificatieproces kunt automatiseren en de beveiliging van uw documenten kunt verbeteren.

### Veelgestelde vragen

#### Vraag: Wat zijn digitale handtekeningen in een Word-document?

A: Digitale handtekeningen in een Word-document zijn elektronische handtekeningen die een manier bieden om de integriteit en oorsprong van het document te verifiëren. Ze worden gemaakt met behulp van digitale certificaten en cryptografische algoritmen, waardoor ontvangers kunnen verifiëren dat het document niet is gewijzigd en dat het afkomstig is van een vertrouwde bron.

#### Vraag: Hoe krijg ik toegang tot digitale handtekeningen in een Word-document met Aspose.Words voor .NET?

A: Om toegang te krijgen tot digitale handtekeningen in een Word-document met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Laad het document met behulp van de`Document` class en geef het pad naar het documentbestand op.
2.  Gebruik een lus om door de`DigitalSignatures` verzameling van het document. Elke iteratie vertegenwoordigt een digitale handtekening.

#### Vraag: Tot welke informatie kan ik toegang krijgen via een digitale handtekening in een Word-document?

A: Vanuit een digitale handtekening in een Word-document heeft u toegang tot verschillende informatie, zoals:
- Geldigheid: Controleer of de handtekening geldig is.
- Opmerkingen: Haal de reden voor ondertekening op, opgegeven door de ondertekenaar.
- Ondertekentijd: verkrijg het tijdstip waarop het document is ondertekend.
- Onderwerpnaam: Haal de naam op van de ondertekenaar of het certificaatonderwerp.
- Naam uitgever: Haal de naam op van de uitgever van het certificaat.

#### Vraag: Kan ik de geldigheid van een digitale handtekening in een Word-document verifiëren met Aspose.Words voor .NET?

 A: Ja, u kunt de geldigheid van een digitale handtekening in een Word-document verifiëren met Aspose.Words voor .NET. Door toegang te krijgen tot de`IsValid` eigendom van de`DigitalSignature` object, kunt u bepalen of de handtekening geldig is of niet.

#### Vraag: Hoe kan ik de geldigheid van digitale handtekeningen in een Word-document verifiëren met Aspose.Words voor .NET?

A: Om de geldigheid van digitale handtekeningen in een Word-document te verifiëren met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Toegang krijgen tot`DigitalSignatures` verzameling van het document.
2.  Herhaal ze allemaal`DigitalSignature` voorwerp in de collectie.
3.  Gebruik de`IsValid` eigendom van de`DigitalSignature` object om te controleren of de handtekening geldig is.

#### Vraag: Kan ik de opmerkingen van de ondertekenaar of de reden voor ondertekening ophalen uit een digitale handtekening in een Word-document?

A: Ja, u kunt de opmerkingen van de ondertekenaar of de reden voor ondertekening ophalen uit een digitale handtekening in een Word-document. De`Comments` eigendom van de`DigitalSignature` object biedt toegang tot de opmerkingen die de ondertekenaar tijdens het ondertekeningsproces heeft opgegeven.

#### Vraag: Welk type documenten ondersteunt de handtekeningverificatiefunctie in Aspose.Words voor .NET?

A: De handtekeningverificatiefunctie in Aspose.Words voor .NET ondersteunt de verificatie van digitale handtekeningen in Word-documenten met het DOCX-bestandsformaat. U kunt deze functie gebruiken om handtekeningen in DOCX-bestanden te verifiëren.

#### Vraag: Hoe kan ik toegang krijgen tot de certificaatgegevens van een digitale handtekening in een Word-document met Aspose.Words voor .NET?

 A: Om toegang te krijgen tot de certificaatgegevens van een digitale handtekening in een Word-document met Aspose.Words voor .NET, kunt u toegang krijgen tot de`CertificateHolder` eigendom van de`DigitalSignature` voorwerp. Van de`CertificateHolder` object, kunt u verschillende details van het certificaat opvragen, zoals de naam van het onderwerp en de naam van de uitgever.

#### Vraag: Kan ik de weergave of verwerking van digitale handtekeningen in een Word-document aanpassen met Aspose.Words voor .NET?

 A: Ja, u kunt de weergave of verwerking van digitale handtekeningen in een Word-document aanpassen met Aspose.Words voor .NET. Door toegang te krijgen tot de eigenschappen en methoden van de`DigitalSignature` object, kunt u de gewenste informatie extraheren, aanvullende validaties uitvoeren of het handtekeningverificatieproces integreren in de workflow van uw toepassing.

#### Vraag: Is het mogelijk om meerdere digitale handtekeningen in een Word-document te verifiëren met Aspose.Words voor .NET?

 A: Ja, het is mogelijk om meerdere digitale handtekeningen in een Word-document te verifiëren met Aspose.Words voor .NET. Door te itereren via de`DigitalSignatures` Als u het document verzamelt, kunt u elke digitale handtekening afzonderlijk openen en verifiëren.

