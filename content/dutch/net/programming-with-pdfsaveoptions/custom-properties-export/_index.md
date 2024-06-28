---
title: Aangepaste eigenschappen exporteren in een PDF-document
linktitle: Aangepaste eigenschappen exporteren in een PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u aangepaste eigenschappen exporteert bij het converteren van documenten naar PDF met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/custom-properties-export/
---

In deze zelfstudie leiden we u door de stappen voor het exporteren van de aangepaste eigenschappen van een document naar een PDF-document met Aspose.Words voor .NET. Door aangepaste eigenschappen te exporteren, kunt u aanvullende informatie opnemen in het gegenereerde PDF-document. Volg onderstaande stappen:

## Stap 1: Een document maken en aangepaste eigenschappen toevoegen

Begin met het maken van een exemplaar van de klasse Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Stap 2: Voeg aangepaste eigenschappen toe
 Voeg vervolgens de gewenste aangepaste eigenschappen toe. Als u bijvoorbeeld een eigenschap "Bedrijf" met de waarde "Apose" wilt toevoegen, gebruikt u de`Add` methode van de CustomDocumentProperties-verzameling:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

U kunt zoveel aangepaste eigenschappen toevoegen als nodig is.

## Stap 3: Stel de PDF-exportopties in

Maak een exemplaar van de klasse PdfSaveOptions en geef op hoe aangepaste eigenschappen moeten worden geëxporteerd:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Met deze optie regelt u de export van aangepaste eigenschappen bij het converteren naar PDF.

## Stap 4: Converteer document naar PDF

 Gebruik de`Save` methode om het document naar PDF te converteren, met vermelding van conversieopties:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Zorg ervoor dat u het juiste pad opgeeft om de geconverteerde PDF op te slaan.

### Voorbeeldbroncode voor het exporteren van aangepaste eigenschappen met Aspose.Words voor .NET

Hier is de volledige broncode om aangepaste eigenschappen uit een document te exporteren met Aspose.Words voor .NET:


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Door deze stappen te volgen, kunt u eenvoudig aangepaste eigenschappen van een document exporteren wanneer u naar PDF converteert met Aspose.Words voor .NET.


## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u aangepaste eigenschappen van een document naar een PDF-document kunt exporteren met behulp van Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u eenvoudig aanvullende informatie in het gegenereerde PDF-document opnemen door de aangepaste eigenschappen van het document te exporteren. Profiteer van de functies van Aspose.Words voor .NET om uw PDF-documenten te personaliseren en te verrijken door aangepaste eigenschappen te exporteren.

### Veel Gestelde Vragen

#### Vraag: Wat is het exporteren van aangepaste eigenschappen naar een PDF-document?
A: Door aangepaste eigenschappen naar een PDF-document te exporteren, kan aanvullende informatie in het gegenereerde PDF-document worden opgenomen. Aangepaste eigenschappen zijn metagegevens die specifiek zijn voor uw document, zoals tags, trefwoorden of inloggegevens. Door deze aangepaste eigenschappen te exporteren, kunt u ze beschikbaar maken voor gebruikers wanneer ze het PDF-document bekijken.

#### Vraag: Hoe kan ik de aangepaste eigenschappen van een document exporteren naar een PDF-document met Aspose.Words voor .NET?
A: Volg deze stappen om de aangepaste eigenschappen van een document naar een PDF-document te exporteren met Aspose.Words voor .NET:

 Maak een exemplaar van de`Document` klas.

 Voeg de gewenste aangepaste eigenschappen toe met behulp van de`CustomDocumentProperties` verzameling. Gebruik bijvoorbeeld de`Add` methode om een eigenschap "Bedrijf" toe te voegen met de waarde "Apose".

 Maak een exemplaar van de`PdfSaveOptions` class en geef op hoe aangepaste eigenschappen moeten worden geëxporteerd met behulp van de`CustomPropertiesExport` eigendom. De`PdfCustomPropertiesExport.Standard` waarde exporteert aangepaste eigenschappen volgens de standaardinstellingen.

 Gebruik de`Save` werkwijze van de`Document` class om het document naar PDF te converteren, waarbij de conversieopties worden gespecificeerd.

#### Vraag: Hoe krijg ik toegang tot aangepaste eigenschappen van een PDF-document?
A: Om toegang te krijgen tot de aangepaste eigenschappen van een PDF-document, kunt u een compatibele PDF-lezer gebruiken die het bekijken van documenteigenschappen ondersteunt. De meeste gangbare PDF-lezers, zoals Adobe Acrobat Reader, bieden toegang tot metadata en eigenschappen van een PDF-document. U vindt deze opties meestal onder het menu 'Bestand' of door met de rechtermuisknop op het document te klikken en 'Eigenschappen' te selecteren.