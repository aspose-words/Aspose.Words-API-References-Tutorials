---
title: Optimaliseer de PDF-grootte met Skip Embedded Arial & Times Roman-lettertypen
linktitle: Optimaliseer de PDF-grootte met Skip Embedded Arial & Times Roman-lettertypen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het genereren van geoptimaliseerde PDF's zonder Arial- en Times Roman-lettertypen in te sluiten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de functie om de PDF-grootte te optimaliseren door de ingesloten Arial- en Times Roman-lettertypen over te slaan naar de metabestandsgrootte met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u de optie voor het insluiten van lettertypen in een document kunt configureren en een PDF kunt genereren zonder de Arial- en Times Roman-lettertypen in te sluiten.

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

## Stap 3: Configureer de opties voor opslaan als PDF met insluiting van lettertypen

 Om het insluiten van Arial- en Times Roman-lettertypen in de gegenereerde PDF over te slaan, moeten we de`PdfSaveOptions` bezwaar maken en instellen`FontEmbeddingMode`eigendom aan`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Stap 4: Sla het document op als PDF zonder ingesloten lettertypen

Ten slotte kunnen we het document in PDF-formaat opslaan met behulp van de eerder geconfigureerde opslagopties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Dat is alles ! U hebt met succes een PDF gegenereerd zonder de Arial- en Times Roman-lettertypen in te sluiten met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode om ingebedde Arial- en Times Roman-lettertypen op metabestandsgrootte over te slaan met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u de insluiting van Arial- en Times Roman-lettertypen in een PDF-document kunt uitschakelen met behulp van Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u een PDF-bestand genereren zonder deze specifieke lettertypen in te sluiten, waardoor de bestandsgrootte kan worden verkleind en een betere documentcompatibiliteit op verschillende platforms kan worden gegarandeerd. Houd rekening met de gevolgen van het uitschakelen van het insluiten van lettertypen wanneer u deze functie gebruikt. Ontdek gerust meer functies van Aspose.Words voor .NET om het genereren van uw PDF-bestanden te optimaliseren.

### Veel Gestelde Vragen

#### Vraag: Wat houdt het insluiten van Arial- en Times Roman-lettertypen in een PDF-document in en waarom is dit belangrijk?
A: Het uitschakelen van de insluiting van Arial- en Times Roman-lettertypen in een PDF-document is het proces waarbij deze lettertypen niet worden opgenomen in het gegenereerde PDF-bestand. Dit kan belangrijk zijn om de grootte van het PDF-bestand te verkleinen door het gebruik van lettertypen te vermijden die al algemeen beschikbaar zijn op PDF-leessystemen. Het kan ook helpen zorgen voor een betere compatibiliteit en een consistente weergave van het PDF-document op verschillende apparaten en platforms.

#### Vraag: Hoe kan ik Aspose.Words voor .NET zo configureren dat de lettertypen Arial en Times Roman niet in een PDF-document worden ingesloten?
A: Volg deze stappen om Aspose.Words voor .NET zo te configureren dat de lettertypen Arial en Times Roman niet in een PDF-document worden ingesloten:

 Stel het mappad in waar uw documenten zich bevinden door te vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Laad het document dat u wilt verwerken met behulp van de`Document` klasse en het opgegeven documentpad.

 Maak een exemplaar van de`PdfSaveOptions` klasse en stel de`FontEmbeddingMode`eigendom aan`PdfFontEmbeddingMode.EmbedAll`. Hierdoor worden alle lettertypen behalve Arial en Times Roman in het gegenereerde PDF-bestand ingesloten.

 Gebruik de`Save` werkwijze van de`Document` object om het document in PDF-formaat op te slaan, waarbij u de eerder geconfigureerde opslagopties opgeeft.

#### Vraag: Wat zijn de voordelen van het uitschakelen van het insluiten van Arial- en Times Roman-lettertypen in een PDF-document?
A: De voordelen van het uitschakelen van de insluiting van Arial- en Times Roman-lettertypen in een PDF-document zijn:

Verkleining van PDF-bestandsgrootte: Door het insluiten van algemeen beschikbare lettertypen zoals Arial en Times Roman te vermijden, kan de PDF-bestandsgrootte worden verkleind, waardoor het gemakkelijker wordt om bestanden op te slaan, te delen en over te dragen.

Betere compatibiliteit: Door lettertypen te gebruiken die algemeen beschikbaar zijn op PDF-leessystemen, zorgt u voor een betere compatibiliteit en een betere weergave van het document op verschillende apparaten en platforms.

#### Vraag: Wat zijn de gevolgen van het uitschakelen van de insluiting van Arial- en Times Roman-lettertypen in een PDF-document?
A: De gevolgen van het uitschakelen van de insluiting van Arial- en Times Roman-lettertypen in een PDF-document zijn als volgt:

Ander uiterlijk: Als de lettertypen Arial en Times Roman niet beschikbaar zijn op het systeem waarop de PDF wordt geopend, worden vervangende lettertypen gebruikt, wat kan resulteren in een ander uiterlijk dan bedoeld.

Leesbaarheidsproblemen: gebruikte vervangende lettertypen zijn mogelijk niet zo leesbaar als de oorspronkelijke lettertypen, wat de leesbaarheid van het document kan beïnvloeden.