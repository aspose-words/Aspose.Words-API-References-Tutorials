---
title: Verklein de PDF-grootte door ingesloten lettertypen uit te schakelen
linktitle: Verklein de PDF-grootte door ingesloten lettertypen uit te schakelen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de PDF-grootte kunt verkleinen door het insluiten van Windows-lettertypen uit te schakelen bij het converteren van documenten naar PDF met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In deze zelfstudie leiden we u door de stappen om de PDF-grootte te verkleinen door het insluiten van Windows-lettertypen in een PDF-document uit te schakelen met Aspose.Words voor .NET. Door het insluiten van lettertypen uit te schakelen, kunt u de grootte van het gegenereerde PDF-bestand verkleinen. Volg onderstaande stappen:

## Stap 1: Het document laden

Begin met het uploaden van het document dat u naar PDF wilt converteren:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Zorg ervoor dat u het juiste pad naar uw document opgeeft.

## Stap 2: Stel de PDF-opslagopties in

Maak een exemplaar van de klasse PdfSaveOptions en geef op hoe lettertypen moeten worden ingesloten:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Met deze optie kunt u de integratie van Windows-lettertypen in het gegenereerde PDF-bestand deactiveren.

## Stap 3: Converteer document naar PDF

 Gebruik de`Save` methode om het document naar PDF te converteren, met vermelding van conversieopties:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Zorg ervoor dat u het juiste pad opgeeft om de geconverteerde PDF op te slaan.

### Voorbeeldbroncode voor het uitschakelen van het insluiten van Windows-lettertypen met Aspose.Words voor .NET

Hier is de volledige broncode om het insluiten van Windows-lettertypen in een PDF-document met Aspose.Words voor .NET uit te schakelen:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// De uitvoer-PDF wordt opgeslagen zonder standaard Windows-lettertypen in te sluiten.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Door deze stappen te volgen, kunt u eenvoudig de insluiting van Windows-lettertypen in een PDF-document uitschakelen met Aspose.Words voor .NET.


## Conclusie

In deze zelfstudie hebben we geleerd hoe u de grootte van een PDF-bestand kunt verkleinen door het insluiten van Windows-lettertypen uit te schakelen met Aspose.Words voor .NET. Door het insluiten van lettertypen uit te schakelen, kunt u de grootte van het gegenereerde PDF-bestand verkleinen, waardoor het gemakkelijker wordt om bestanden op te slaan, te delen en over te dragen. Het is echter belangrijk op te merken dat het uitschakelen van het insluiten van Windows-lettertypen wijzigingen in het uiterlijk en de opmaak van het uiteindelijke PDF-document kan veroorzaken. Houd rekening met deze gevolgen wanneer u deze functie gebruikt. Ontdek gerust meer functies van Aspose.Words voor .NET om het genereren van uw PDF-bestanden te optimaliseren.

### Veel Gestelde Vragen

#### Vraag: Wat is het uitschakelen van het insluiten van Windows-lettertypen in een PDF-document en waarom is dit belangrijk?
A: Het uitschakelen van het insluiten van Windows-lettertypen in een PDF-document is het proces waarbij wordt voorkomen dat Windows-lettertypen worden opgenomen in het gegenereerde PDF-bestand. Hierdoor wordt de grootte van het PDF-bestand kleiner door ingesloten Windows-lettertypegegevens te verwijderen. Dit kan belangrijk zijn om de grootte van PDF-bestanden te verkleinen, waardoor ze gemakkelijker kunnen worden opgeslagen, gedeeld en sneller worden overgedragen.

#### Vraag: Hoe kan ik het insluiten van Windows-lettertypen in een PDF-document uitschakelen met Aspose.Words voor .NET?
A: Volg deze stappen om het insluiten van Windows-lettertypen in een PDF-document met Aspose.Words voor .NET uit te schakelen:

 Laad het document dat u naar PDF wilt converteren met behulp van de`Document` klasse- en documentpad.

 Maak een exemplaar van de`PdfSaveOptions` klasse en stel de`FontEmbeddingMode`eigendom aan`PdfFontEmbeddingMode.EmbedNone`. Hierdoor wordt de insluiting van Windows-lettertypen in het gegenereerde PDF-bestand uitgeschakeld.

 Gebruik de`Save` werkwijze van de`Document` object om het document naar PDF te converteren, waarbij u de eerder geconfigureerde conversie-opties opgeeft.

#### Vraag: Wat zijn de voordelen van het uitschakelen van het insluiten van Windows-lettertypen in een PDF-document?
A: De voordelen van het uitschakelen van het insluiten van Windows-lettertypen in een PDF-document zijn:

Verkleinde PDF-bestandsgrootte: Door het insluiten van Windows-lettertypen uit te schakelen, worden ingesloten Windows-lettertypegegevens verwijderd, waardoor de grootte van het gegenereerde PDF-bestand kleiner wordt.

Gemakkelijker opslaan: Kleinere PDF-bestanden zijn gemakkelijker op te slaan, op te slaan en over te dragen.

Sneller delen en overbrengen: Kleinere PDF-bestanden kunnen sneller worden gedeeld en overgedragen, waardoor tijd en middelen worden bespaard.

#### Vraag: Wat zijn de gevolgen van het uitschakelen van het insluiten van Windows-lettertypen in een PDF-document?
A: Het uitschakelen van de insluiting van Windows-lettertypen in een PDF-document kan tot gevolgen leiden zoals:

Verlies van uiterlijk en opmaak: Als de in het document opgegeven Windows-lettertypen niet beschikbaar zijn op het systeem waarop de PDF wordt geopend, worden vervangende lettertypen gebruikt, wat kan resulteren in een onjuist uiterlijk en een onjuiste opmaak. anders van vorm dan verwacht.

Problemen met de leesbaarheid: als de gebruikte vervangende lettertypen niet zo leesbaar zijn als de originele lettertypen, kan dit de leesbaarheid van de tekst in het PDF-document beïnvloeden.