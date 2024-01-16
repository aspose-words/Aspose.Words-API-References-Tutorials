---
title: Update de laatst afgedrukte eigenschap in het PDF-document
linktitle: Update de laatst afgedrukte eigenschap in het PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het bijwerken van de eigenschap 'Laatst afgedrukt' bij het converteren naar PDF met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de eigenschap 'Laatste afdruk' in de updatefunctie voor PDF-documenten met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze tutorial zult u begrijpen hoe u de optie kunt configureren om de eigenschap "Laatst afgedrukt" bij te werken bij het converteren naar PDF.

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

## Stap 3: Configureer de opties voor Opslaan als PDF met bijgewerkte eigenschap "Laatst afgedrukt".

 Om het bijwerken van de eigenschap "Laatst afgedrukt" mogelijk te maken bij het converteren naar PDF, moeten we de`PdfSaveOptions` bezwaar maken en instellen`UpdateLastPrintedProperty`eigendom aan`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Stap 4: Sla het document op als PDF met de update van de eigenschap "Laatst afgedrukt".

Ten slotte kunnen we het document in PDF-formaat opslaan met behulp van de eerder geconfigureerde opslagopties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Dat is alles ! U hebt het bijwerken van de eigenschap 'Laatst afgedrukt' ingeschakeld bij het converteren van een document naar PDF met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het bijwerken van de eigenschap 'Laatst afgedrukt' met Aspose.Words voor .NET


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u de eigenschap "Laatst afgedrukt" in een PDF-document kunt bijwerken met Aspose.Words voor .NET. Door de gegeven stappen te volgen, kunt u eenvoudig de optie configureren om de eigenschap "Laatst afgedrukt" bij te werken bij het converteren van een document naar PDF. Gebruik deze functie om het documentgebruik en gerelateerde informatie bij te houden.

### Veel Gestelde Vragen

#### Vraag: Wat is de eigenschap 'Laatst afgedrukt' in een PDF-document?
A: De eigenschap "Laatst afgedrukt" in een PDF-document verwijst naar de datum en tijd waarop het document voor het laatst is afgedrukt. Deze eigenschap kan handig zijn voor het bijhouden van informatie over documentgebruik en -beheer.

#### Vraag: Hoe kan ik de eigenschap "Laatst afgedrukt" in een PDF-document bijwerken met Aspose.Words voor .NET?
A: Volg deze stappen om de eigenschap 'Laatst afgedrukt' in een PDF-document met Aspose.Words voor .NET bij te werken:

 Maak een exemplaar van de`Document` klasse die het pad naar het Word-document specificeert.

 Maak een exemplaar van de`PdfSaveOptions` klasse en stel de`UpdateLastPrintedProperty`eigendom aan`true` om het bijwerken van de eigenschap 'Laatst afgedrukt' mogelijk te maken.

 Gebruik de`Save` werkwijze van de`Document`class om het document in PDF-indeling op te slaan door opslagopties op te geven.

#### Vraag: Hoe kan ik controleren of de eigenschap "Laatst afgedrukt" is bijgewerkt in het gegenereerde PDF-document?
A: U kunt controleren of de eigenschap "Laatst afgedrukt" is bijgewerkt in het gegenereerde PDF-document door het PDF-bestand te openen met een compatibele PDF-viewer, zoals Adobe Acrobat Reader, en de documentinformatie te bekijken. De datum en tijd van de laatste afdruk moeten overeenkomen met de datum en tijd van het genereren van het PDF-document.
