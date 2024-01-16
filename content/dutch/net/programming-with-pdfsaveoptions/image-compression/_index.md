---
title: Beeldcompressie in een PDF-document
linktitle: Beeldcompressie in een PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het comprimeren van afbeeldingen in een PDF-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/image-compression/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de functie Beeldcompressie in een PDF-document met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u afbeeldingen in een document kunt comprimeren en een PDF kunt genereren met de juiste beeldcompressie.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar uw documenten zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Upload het document

Vervolgens moeten we het document laden dat we willen verwerken. In dit voorbeeld gaan we ervan uit dat het document "Rendering.docx" heet en zich in de opgegeven documentenmap bevindt.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Configureer de opties voor opslaan als PDF met beeldcompressie

 Om afbeeldingen te comprimeren bij het converteren naar PDF, moeten we de`PdfSaveOptions` voorwerp. Indien nodig kunnen we het type beeldcompressie, JPEG-kwaliteit en andere PDF-compatibiliteitsopties instellen.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Stap 4: Document opslaan als PDF met beeldcompressie

Ten slotte kunnen we het document in PDF-formaat opslaan met behulp van de eerder geconfigureerde opslagopties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Stap 5: Configureer opties voor het opslaan naar PDF/A-2u met beeldcompressie

Als u een PDF/A-2u-compatibele PDF met beeldcompressie wilt genereren, kunt u de aanvullende opslagopties configureren.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Gebruik JPEG-compressie met 50% kwaliteit om de bestandsgrootte te verkleinen.
};
```

## Stap 6: Sla het document op als PDF/A-2u met beeldcompressie

Sla het document op in PDF/A-2u-indeling met behulp van de extra opslagopties die eerder zijn geconfigureerd.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Dat is alles ! U hebt de afbeeldingen in een document met succes gecomprimeerd en een PDF met de juiste beeldcompressie gegenereerd met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het comprimeren van afbeeldingen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Gebruik JPEG-compressie met een kwaliteit van 50% om de bestandsgrootte te verkleinen.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u afbeeldingen in een PDF-document comprimeert met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u eenvoudig de grootte van afbeeldingen in uw PDF-document verkleinen en een PDF genereren met de juiste beeldcompressie. Gebruik de beeldcompressiefuncties van Aspose.Words voor .NET om de grootte van uw PDF-documenten te optimaliseren met behoud van de beeldkwaliteit.

### Veel Gestelde Vragen

#### Vraag: Wat is beeldcompressie in een PDF-document?
A: Het comprimeren van afbeeldingen in een PDF-document is bedoeld om de grootte van de afbeeldingen in het PDF-document te verkleinen om de totale grootte van het PDF-bestand te verkleinen. Dit vermindert de benodigde opslagruimte en verbetert de prestaties bij het laden en bekijken van de PDF.

#### Vraag: Hoe kan ik afbeeldingen in een PDF-document comprimeren met Aspose.Words voor .NET?
A: Volg deze stappen om afbeeldingen in een PDF-document te comprimeren met Aspose.Words voor .NET:

 Maak een exemplaar van de`Document` klasse die het pad naar het Word-document specificeert.

 Maak een exemplaar van de`PdfSaveOptions` klasse en stel de`ImageCompression`eigendom aan`PdfImageCompression.Jpeg` om JPEG-compressie te gebruiken.

U kunt ook andere opties voor beeldcompressie instellen, zoals JPEG-kwaliteit, afhankelijk van uw behoeften.

 Gebruik de`Save` werkwijze van de`Document`class om het document in PDF-indeling op te slaan door opslagopties op te geven.

#### Vraag: Wat is het verschil tussen standaardbeeldcompressie en PDF/A-2u-beeldcompressie?
A: Standaardafbeeldingscompressie verkleint de grootte van afbeeldingen in een PDF-document terwijl de formuliervelden behouden blijven. Hierdoor wordt de totale grootte van het PDF-bestand kleiner, zonder dat dit ten koste gaat van de functionaliteit van het formulierveld.

Beeldcompressie met PDF/A-2u is een extra optie waarmee u een PDF-bestand kunt genereren dat voldoet aan de PDF/A-2u-standaard terwijl u beeldcompressie toepast. PDF/A-2u is een ISO-standaard voor archief-PDF-documenten en garandeert de langdurige bewaring van documenten.
