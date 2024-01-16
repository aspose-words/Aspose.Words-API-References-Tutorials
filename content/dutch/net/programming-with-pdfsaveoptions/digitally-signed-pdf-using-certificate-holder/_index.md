---
title: Voeg digitale handtekening toe aan PDF met behulp van Certificaathouder
linktitle: Voeg digitale handtekening toe aan PDF met behulp van Certificaathouder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een digitale handtekening aan PDF kunt toevoegen met Certificaathouder met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In deze zelfstudie leiden we u door de stappen om een digitale handtekening aan PDF toe te voegen met behulp van de certificaathouder met Aspose.Words voor .NET. De digitale handtekening voegt een laag beveiliging en integriteit toe aan het PDF-document. Volg onderstaande stappen:

## Stap 1: Het document maken en inhoud toevoegen

Begin met het maken van een exemplaar van de klasse Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg inhoud toe aan het document

 Gebruik dan de`DocumentBuilder`om inhoud aan het document toe te voegen. Als u bijvoorbeeld een alinea wilt toevoegen die de tekst "Test Signed PDF" bevat, gebruikt u de`Writeln` methode:

```csharp
builder.Writeln("Test Signed PDF.");
```

U kunt indien nodig andere inhoudsitems toevoegen.

## Stap 3: Stel de PDF-opslagopties in

Maak een exemplaar van de klasse PdfSaveOptions en geef de details van de digitale handtekening op:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Zorg ervoor dat u het juiste pad naar uw certificaat en het bijbehorende wachtwoord opgeeft. U kunt ook de reden en locatie van de handtekening aanpassen.

## Stap 4: Document opslaan als digitaal ondertekende PDF

 Gebruik de`Save` methode om het document als PDF op te slaan door de opslagopties op te geven:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Zorg ervoor dat u het juiste pad opgeeft om de digitaal ondertekende PDF op te slaan.

Door deze stappen te volgen, kunt u eenvoudig een digitaal ondertekende PDF met certificaat maken met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor digitaal ondertekende pdf met certificaathouder met Aspose.Words voor .NET

Hier is de volledige broncode voor digitaal ondertekende pdf met certificaathouder uit een document met Aspose.Words voor .NET:

```csharp

            // Het pad naar de documentenmap.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Conclusie

In deze zelfstudie hebben we de stappen onderzocht waarmee u een digitale handtekening aan een PDF-document kunt toevoegen met behulp van een certificaat met Aspose.Words voor .NET. De digitale handtekening voegt een beveiligings- en integriteitslaag toe aan het document, waardoor de authenticiteit ervan wordt gegarandeerd en het mogelijk wordt gemaakt om eventuele latere wijzigingen te detecteren. Door de gegeven stappen te volgen, kunt u eenvoudig een digitaal ondertekende PDF maken met behulp van een certificaat met Aspose.Words voor .NET.

### Veel Gestelde Vragen

#### Vraag: Wat is een digitale handtekening en waarom is deze belangrijk in een PDF-document?
A: Een digitale handtekening is een beveiligingstechniek die de authenticiteit, integriteit en onweerlegbaarheid van een elektronisch document, zoals een PDF-bestand, helpt garanderen. Het maakt gebruik van een digitaal certificaat om een beveiligingslaag aan het document toe te voegen, waardoor de identiteit van de auteur wordt geverifieerd en eventuele latere wijzigingen in de inhoud worden gedetecteerd.

#### Vraag: Hoe kan ik een digitale handtekening toevoegen aan een PDF-document met behulp van een certificaat met Aspose.Words voor .NET?
A: Volg deze stappen om een digitale handtekening aan een PDF-document toe te voegen met behulp van een certificaat met Aspose.Words voor .NET:

 Maak een exemplaar van de`Document` klasse om het document weer te geven.

 Gebruik de`DocumentBuilder` class om de gewenste inhoud aan het document toe te voegen.

 Maak een exemplaar van de`PdfSaveOptions` class en specificeer de details van de digitale handtekening met behulp van de`PdfDigitalSignatureDetails` klas. U moet het pad naar het certificaat opgeven (`CertificateHolder.Create`), het bijbehorende wachtwoord en de reden en locatie van de ondertekening.

 Gebruik de`Save` methode om het document in PDF-formaat op te slaan, waarbij de opslagopties worden gespecificeerd.

#### Vraag: Hoe verkrijg ik een certificaat om een digitale handtekening aan een PDF-document toe te voegen?
A: Om een certificaat te verkrijgen waarmee u een digitale handtekening aan een PDF-document kunt toevoegen, kunt u doorgaans contact opnemen met een certificeringsinstantie (CA) of een vertrouwensdienstverlener. Deze entiteiten geven digitale certificaten uit nadat ze uw identiteit hebben geverifieerd en uw verzoek hebben gevalideerd. Zodra u een certificaat heeft verkregen, kunt u dit in uw toepassing gebruiken om digitale handtekeningen aan PDF-documenten toe te voegen.

#### Vraag: Is het mogelijk om de details van de digitale handtekening, zoals reden en locatie, aan te passen?
 A: Ja, u kunt de details van de digitale handtekening aanpassen door de reden en locatie van de handtekening op te geven. In de gegeven voorbeeldcode kunt u de waarden van de`reason` En`location` parameters bij het maken van de`PdfDigitalSignatureDetails` voorwerp. Zorg ervoor dat u voor elke parameter de juiste informatie verstrekt om de reden en locatie van de handtekening in uw PDF-document weer te geven.