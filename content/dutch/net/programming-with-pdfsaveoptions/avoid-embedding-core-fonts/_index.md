---
title: Verklein de PDF-bestandsgrootte door geen kernlettertypen in te sluiten
linktitle: Verklein de PDF-bestandsgrootte door geen kernlettertypen in te sluiten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de PDF-bestandsgrootte kunt verkleinen door geen kernlettertypen in te sluiten bij het converteren van Word-documenten naar PDF met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In deze zelfstudie leiden we u door de stappen voor het verkleinen van de PDF-bestandsgrootte door geen kernlettertypen in te sluiten met Aspose.Words voor .NET. Met deze functie kunt u bepalen of basislettertypen zoals Arial, Times New Roman, enz. in de PDF moeten worden ingesloten bij het converteren van een Word-document. Volg onderstaande stappen:

## Stap 1: Het document laden

Begin met het uploaden van het Word-document dat u naar PDF wilt converteren:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Zorg ervoor dat u het juiste pad naar uw Word-document opgeeft.

## Stap 2: Stel PDF-conversieopties in

Maak een exemplaar van de klasse PdfSaveOptions en schakel het vermijden van basisinsluiting van lettertypen in:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Deze optie bepaalt of basislettertypen in de PDF moeten worden ingesloten of niet.

## Stap 3: Converteer document naar PDF

 Gebruik de`Save` methode om het Word-document naar PDF te converteren door conversieopties op te geven:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Zorg ervoor dat u het juiste pad opgeeft om de geconverteerde PDF op te slaan.

### Voorbeeldbroncode voor het vermijden van het insluiten van kernlettertypen met Aspose.Words voor .NET

Hier is de volledige broncode om de functie te gebruiken om het insluiten van kernlettertypen met Aspose.Words voor .NET te voorkomen:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// De uitvoer-PDF wordt niet ingesloten met kernlettertypen zoals Arial, Times New Roman enz.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Door deze stappen te volgen, kunt u eenvoudig bepalen of basislettertypen in de PDF moeten worden ingesloten bij het converteren van een Word-document met Aspose.Words voor .NET.


## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u de grootte van een PDF-bestand kunt verkleinen door geen basislettertypen in te sluiten met Aspose.Words voor .NET. Met deze functie kunt u bepalen of basislettertypen in de PDF moeten worden ingesloten bij het converteren van een Word-document. Door de beschreven stappen te volgen, kunt u eenvoudig het insluiten of niet-insluiten van basislettertypen beheren, wat kan helpen de PDF-bestandsgrootte te verkleinen en een betere compatibiliteit en een consistent uiterlijk van het document op verschillende apparaten en platforms te garanderen. Vergeet niet de gevolgen te overwegen als u geen basislettertypen insluit en experimenteer om ervoor te zorgen dat het document wordt weergegeven zoals verwacht.

### Veel Gestelde Vragen

#### Vraag: Wat is de optie om geen basislettertypen in een PDF-bestand in te sluiten en waarom is dit belangrijk?
A: De optie om geen basislettertypen in een PDF-bestand in te sluiten, bepaalt of basislettertypen zoals Arial, Times New Roman, enz. in de PDF moeten worden ingesloten bij het converteren van een Word-document. Dit kan belangrijk zijn om de grootte van het PDF-bestand te verkleinen door te voorkomen dat lettertypen worden gebruikt die algemeen beschikbaar zijn op PDF-leessystemen. Het kan ook helpen zorgen voor een betere compatibiliteit en een consistente weergave van het PDF-document op verschillende apparaten en platforms.

#### Vraag: Hoe kan ik Aspose.Words voor .NET zo configureren dat er geen basislettertypen in een PDF-bestand worden ingesloten?
A: Volg deze stappen om Aspose.Words voor .NET zo te configureren dat er geen kernlettertypen in een PDF-bestand worden ingesloten:

 Stel het mappad in waar uw documenten zich bevinden door te vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Laad het Word-document dat u naar PDF wilt converteren met behulp van de`Document` klasse en het opgegeven documentpad.

 Maak een exemplaar van de`PdfSaveOptions` klasse en stel de`UseCoreFonts`eigendom aan`true`. Dit voorkomt het insluiten van basislettertypen in het gegenereerde PDF-bestand.

 Gebruik de`Save` werkwijze van de`Document` object om het document in PDF-indeling op te slaan, waarbij de eerder geconfigureerde conversie-opties worden opgegeven.

#### Vraag: Wat zijn de voordelen van het niet insluiten van basislettertypen in een PDF-bestand?
A: De voordelen van het niet insluiten van basislettertypen in een PDF-bestand zijn:

Verkleining van de PDF-bestandsgrootte: Door het insluiten van algemeen beschikbare lettertypen zoals Arial, Times New Roman, enz. te vermijden, kan de PDF-bestandsgrootte worden verkleind, waardoor het gemakkelijker wordt om bestanden op te slaan, te delen en over te dragen.

Betere compatibiliteit: Door basislettertypen te gebruiken die algemeen beschikbaar zijn op PDF-leessystemen, zorgt u voor een betere compatibiliteit en documentuiterlijk op verschillende apparaten en platforms.

#### Vraag: Wat zijn de gevolgen als er geen basislettertypen in een PDF-bestand worden ingesloten?
A: De gevolgen van het niet insluiten van basislettertypen in een PDF-bestand zijn als volgt:

Ander uiterlijk: Als de basislettertypen niet beschikbaar zijn op het systeem waarop de PDF wordt geopend, worden vervangende lettertypen gebruikt, wat kan resulteren in een ander uiterlijk dan bedoeld.

Problemen met de leesbaarheid: gebruikte vervangende lettertypen zijn mogelijk niet zo leesbaar als de originele lettertypen, wat de leesbaarheid van het document kan beïnvloeden.