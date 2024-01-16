---
title: Verklein de PDF-grootte door WMF-lettertypen te schalen naar metabestandsgrootte
linktitle: Verklein de PDF-grootte door WMF-lettertypen te schalen naar metabestandsgrootte
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om de pdf-grootte te verkleinen door wmf-lettertypen te schalen naar de grootte van metabestanden bij het converteren naar pdf met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Dit artikel biedt een stapsgewijze handleiding voor het verkleinen van de pdf-grootte met de functie WMF-lettertypen schalen naar metabestandsgrootte met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u de schaal van WMF-lettertypen kunt in- of uitschakelen bij het converteren naar PDF.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar uw documenten zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Upload het document

Vervolgens moeten we het document laden dat we willen verwerken. In dit voorbeeld gaan we ervan uit dat het document "WMF met text.docx" heet en zich in de opgegeven documentenmap bevindt.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Stap 3: Configureer de weergaveopties voor metabestanden

 Om het schalen van WMF-lettertypen naar metabestandsgrootte in of uit te schakelen, moeten we de`MetafileRenderingOptions`voorwerp. In dit voorbeeld schakelen we het schalen van lettertypen uit door de`ScaleWmfFontsToMetafileSize`eigendom aan`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Stap 4: Configureer de opties voor opslaan als PDF met weergaveopties voor metabestanden

Ten slotte kunnen we de opties voor opslaan naar PDF configureren met behulp van de eerder geconfigureerde weergaveopties voor metabestanden.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Stap 5: Document opslaan als PDF met weergaveopties voor metabestanden

Sla het document op in PDF-formaat met behulp van de eerder geconfigureerde opslagopties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Dat is alles ! U hebt tijdens het converteren het schalen van WMF-lettertypen naar metabestandsgrootte met succes in- of uitgeschakeld

een PDF-document met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het schalen van WMF-lettertypen naar metabestandsgrootte met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Als Aspose.Words sommige metabestandsrecords niet correct kan weergeven in vectorafbeeldingen
	// vervolgens rendert Aspose.Words dit metabestand naar een bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u het formaat van WMF-lettertypen naar metabestandsgrootte in een PDF-document kunt in- of uitschakelen met behulp van Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u eenvoudig bepalen of de grootte van WMF-lettertypen moet worden aangepast aan de grootte van het metabestand bij het converteren naar een PDF-document. Dit kan u helpen de grootte van het gegenereerde PDF-bestand te verkleinen en de weergaveprestaties te verbeteren. Zorg ervoor dat u het juiste pad naar uw documenten opgeeft en configureer indien nodig de weergaveopties voor metabestanden.

### Veel Gestelde Vragen

#### Vraag: Wat betekent het wijzigen van de grootte van WMF-lettertypen naar metabestandsgrootte in een PDF-document?
A: Het formaat van WMF-lettertypen aanpassen aan de grootte van metabestanden in een PDF-document is een functie die bepaalt of WMF-lettertypen moeten worden geschaald zodat ze overeenkomen met de grootte van het metabestand bij het converteren naar een PDF-document. Wanneer deze functie is ingeschakeld, worden WMF-lettertypen geschaald zodat ze overeenkomen met de grootte van het metabestand, waardoor de grootte van het gegenereerde PDF-document mogelijk kleiner wordt.

#### Vraag: Hoe kan ik Aspose.Words voor .NET gebruiken om het wijzigen van de grootte van WMF-lettertypen naar metabestandsgrootte in een PDF-document in of uit te schakelen?
A: Om het formaat van WMF-lettertypen naar metabestandsgrootte in een PDF-document met Aspose.Words voor .NET in of uit te schakelen, volgt u deze stappen:

 Stel het mappad in waar uw documenten zich bevinden door te vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Laad het document dat u wilt verwerken met behulp van de`Document` class en specificeer het pad naar het Word-document in de opgegeven documentenmap.

 Configureer de weergaveopties voor metabestanden door een exemplaar te maken van het`MetafileRenderingOptions` klasse en het instellen van de`ScaleWmfFontsToMetafileSize`eigendom aan`true` om het schalen van WMF-lettertypen naar metabestandsgrootte mogelijk te maken, of naar`false` om deze functie uit te schakelen.

 Configureer de opties voor opslaan als PDF door een exemplaar te maken van het`PdfSaveOptions` class en met behulp van de eerder geconfigureerde weergaveopties voor metabestanden.

 Sla het document op in PDF-formaat met behulp van de`Save` werkwijze van de`Document` klasse die het pad specificeert en opties voor opslaan.

#### Vraag: Wat zijn de voordelen van het wijzigen van de grootte van WMF-lettertypen naar metabestandsgrootte in een PDF-document?
A: De voordelen van het wijzigen van de grootte van WMF-lettertypen naar metabestandsgrootte in een PDF-document zijn:

Verkleining van de PDF-bestandsgrootte: Door de grootte van WMF-lettertypen aan te passen aan de metabestandsgrootte kan de grootte van het gegenereerde PDF-document worden verkleind door de lettergrootte aan te passen aan de behoeften van de metabestanden.

Verbeterde prestaties: Door de grootte van WMF-lettertypen aan te passen aan de afmetingen van het metabestand, kan de weergave van het PDF-document sneller en efficiënter zijn.