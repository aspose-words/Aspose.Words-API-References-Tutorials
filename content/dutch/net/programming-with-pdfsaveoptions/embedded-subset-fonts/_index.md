---
title: Subsetlettertypen insluiten in PDF-document
linktitle: Subsetlettertypen insluiten in PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het insluiten van lettertypesubsets in een PDF-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de insluitingsfunctie voor lettertypesubsets met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u subsets van lettertypen in een document kunt insluiten en een PDF kunt genereren met alleen de glyphs die in het document worden gebruikt.

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

## Stap 3: Configureer de opties voor opslaan als PDF

 Om een PDF te maken die alleen de subsets van lettertypen bevat die in het document worden gebruikt, moeten we de`PdfSaveOptions` bezwaar maken met de`EmbedFullFonts` eigenschap ingesteld`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Stap 4: Document opslaan als PDF met subsets van lettertypen

 Ten slotte kunnen we het document opslaan als PDF met behulp van de lettertypesubsets. Geef de naam van het uitvoerbestand op en de`saveOptions` object dat we in de vorige stap hebben geconfigureerd.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Dat is alles ! U hebt met succes subsets van lettertypen in een document ingesloten en een PDF gegenereerd met alleen de glyphs die in het document worden gebruikt met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het insluiten van lettertypesubsets met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// De uitvoer-PDF bevat subsets van de lettertypen in het document.
	// Alleen de glyphs die in het document worden gebruikt, zijn opgenomen in de PDF-lettertypen.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u subsets van lettertypen in een PDF-document kunt insluiten met behulp van Aspose.Words voor .NET. Door subsets van lettertypen in te sluiten, kunt u de grootte van het PDF-bestand verkleinen, terwijl het uiterlijk van het document behouden blijft, doordat alleen de daadwerkelijk gebruikte tekens worden gebruikt. Dit zorgt voor betere compatibiliteit en prestaties bij het bekijken en afdrukken van de PDF. Voel je vrij om de functies van Aspose.Words voor .NET verder te verkennen om het genereren van je PDF-documenten met ingebedde lettertypesubsets te optimaliseren.

### Veel Gestelde Vragen

#### Vraag: Wat is het insluiten van lettertypesubsets in een PDF-document?
A: Het insluiten van subsets van lettertypen in een PDF-document is het proces waarbij alleen de glyphs worden opgenomen die in het document worden gebruikt, in plaats van alle volledige lettertypen. Dit verkleint de grootte van het PDF-bestand door alleen de lettertypegegevens op te nemen die nodig zijn om de tekens weer te geven die daadwerkelijk in het document worden gebruikt.

#### Vraag: Wat is het verschil tussen het insluiten van volledige lettertypen en het insluiten van subsets van lettertypen?
A: Volledige lettertype-insluiting betekent dat alle lettertypen die in het document worden gebruikt in het PDF-bestand worden opgenomen. Dit zorgt ervoor dat het document precies wordt weergegeven zoals het is ontworpen, maar kan de grootte van het PDF-bestand vergroten. Daarentegen bevat het insluiten van subsets van lettertypen alleen de glyphs die in het document worden gebruikt, waardoor de grootte van het PDF-bestand wordt verkleind, maar de mogelijkheid wordt beperkt om het uiterlijk van het document exact te repliceren als er later extra tekens worden toegevoegd.

#### Vraag: Hoe kan ik subsets van lettertypen insluiten in een PDF-document met Aspose.Words voor .NET?
A: Volg deze stappen om subsets van lettertypen in een PDF-document in te sluiten met Aspose.Words voor .NET:

 Stel het documentmappad in door te vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Laad het document dat u wilt verwerken met behulp van de`Document` klasse en het documentpad.

 Configureer de opties voor het opslaan van PDF's door een exemplaar te maken van het`PdfSaveOptions` klasse en het instellen van de`EmbedFullFonts`eigendom aan`false`Dit zorgt ervoor dat alleen de lettertypesubsets die in het document worden gebruikt, in het PDF-bestand worden opgenomen.

 Sla het document op in PDF-indeling met de lettertypesubsets ingebed met behulp van de`Save` werkwijze van de`Document` object, waarbij u de naam van het uitvoerbestand en de eerder geconfigureerde opslagopties opgeeft.

#### Vraag: Wat zijn de voordelen van het insluiten van lettertypesubsets in een PDF-document?
A: De voordelen van het insluiten van lettertypesubsets in een PDF-document zijn:

Verkleinde PDF-bestandsgrootte: Door alleen de glyphs op te nemen die in het document worden gebruikt, wordt de PDF-bestandsgrootte verkleind in vergelijking met het insluiten van volledige lettertypen.

Behoud van het uiterlijk van het document: De subsets van lettertypen in het PDF-bestand maken het mogelijk om het uiterlijk van het document te reproduceren met alleen de daadwerkelijk gebruikte tekens.

Compatibiliteit met de beperkingen van de licentie: Het insluiten van subsets van lettertypen kan de voorkeur hebben in gevallen waarin volledige lettertypen niet legaal kunnen worden ingesloten vanwege licentiebeperkingen.