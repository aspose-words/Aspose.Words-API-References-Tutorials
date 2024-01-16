---
title: Exporteer de Word-documentstructuur naar een PDF-document
linktitle: Exporteer de Word-documentstructuur naar een PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van de Word-documentstructuur naar een PDF-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/export-document-structure/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de functie Word-documentstructuur exporteren naar PDF-document met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u de structuur van een document kunt exporteren en een PDF kunt genereren waarin de structuur van het document zichtbaar is.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar uw documenten zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Upload het document

Vervolgens moeten we het document laden dat we willen verwerken. In dit voorbeeld gaan we ervan uit dat het document "Paragraphs.docx" heet en zich in de opgegeven documentenmap bevindt.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Stap 3: Configureer de opties voor opslaan als PDF

 Om de documentstructuur te exporteren en de structuur zichtbaar te maken in het navigatievenster "Inhoud" van Adobe Acrobat Pro tijdens het bewerken van het PDF-bestand, moeten we de`PdfSaveOptions` bezwaar maken met de`ExportDocumentStructure` eigenschap ingesteld`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Stap 4: Sla het document op als PDF met de documentstructuur

Ten slotte kunnen we het document in PDF-formaat opslaan met behulp van de eerder geconfigureerde opslagopties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Dat is alles ! U hebt met succes een documentstructuur geëxporteerd en een PDF gegenereerd waarbij de documentstructuur zichtbaar is met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het exporteren van de documentstructuur met Aspose.Words voor .NET


```csharp

            // Het pad naar de documentenmap.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // De bestandsgrootte wordt vergroot en de structuur wordt zichtbaar in het navigatievenster "Inhoud".
            // van Adobe Acrobat Pro, tijdens het bewerken van de .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Conclusie

In deze tutorial hebben we uitgelegd hoe je de structuur van een Word-document naar een PDF-document kunt exporteren met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u eenvoudig een PDF genereren waarin uw documentstructuur zichtbaar is, waardoor u gemakkelijker door het document kunt navigeren en zoeken. Gebruik de functies van Aspose.Words voor .NET om de structuur van uw Word-documenten te exporteren en goed gestructureerde PDF's te maken.

### Veel Gestelde Vragen

#### Vraag: Wat is het exporteren van de structuur van een Word-document naar een PDF-document?
A: Door de structuur van een Word-document naar een PDF-document te exporteren, ontstaat een PDF met een zichtbare documentstructuur. De documentstructuur omvat meestal zaken als koppen, secties, alinea's en andere gestructureerde elementen van het document. Deze structuur kan handig zijn voor navigatie en zoeken in het PDF-document.

#### Vraag: Hoe kan ik de structuur van een Word-document exporteren naar een PDF-document met Aspose.Words voor .NET?
A: Volg deze stappen om de structuur van een Word-document naar een PDF-document te exporteren met Aspose.Words voor .NET:

 Maak een exemplaar van de`Document` klasse die het pad naar het Word-document specificeert.

 Maak een exemplaar van de`PdfSaveOptions` klasse en stel de`ExportDocumentStructure`eigendom aan`true`. Hierdoor wordt de documentstructuur geëxporteerd en zichtbaar gemaakt in het navigatievenster "Inhoud" van Adobe Acrobat Pro wanneer u het PDF-bestand bewerkt.

 Gebruik de`Save` werkwijze van de`Document`class om het document in PDF-indeling op te slaan door opslagopties op te geven.

#### Vraag: Hoe kan ik de structuur van een PDF-document bekijken met Adobe Acrobat Pro?
A: Volg deze stappen om de structuur van een PDF-document te bekijken met Adobe Acrobat Pro:

Open het PDF-document in Adobe Acrobat Pro.

Klik in de linkernavigatiebalk op het pictogram 'Inhoud' om het navigatievenster 'Inhoud' weer te geven.

In het navigatievenster "Inhoud" ziet u de documentstructuur met koppen, secties en andere gestructureerde elementen.