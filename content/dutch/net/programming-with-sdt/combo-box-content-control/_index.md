---
title: Inhoudscontrole van keuzelijst met invoervak
linktitle: Inhoudscontrole van keuzelijst met invoervak
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een Combo Box Content Control in een Word-document kunt maken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/combo-box-content-control/
---

In deze tutorial wordt uitgelegd hoe u een Combo Box Content Control in een Word-document kunt maken met behulp van Aspose.Words voor .NET. Met de inhoudsbesturingselementen voor keuzelijsten met keuzelijst kunnen gebruikers een item uit een vervolgkeuzelijst selecteren.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een document en StructuredDocumentTag
 Maak een nieuw exemplaar van de`Document` klasse en een`StructuredDocumentTag` om het inhoudsbeheer van de keuzelijst met invoervak weer te geven. Specificeer`SdtType.ComboBox` als het type en`MarkupLevel.Block` als het opmaakniveau om een keuzelijst met invoervak op blokniveau te maken.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Stap 3: Voeg items toe aan de keuzelijst met invoervak
 Voeg items toe aan de keuzelijst met invoervak met behulp van de`ListItems` eigendom van de`StructuredDocumentTag` Elk item wordt vertegenwoordigd door een`SdtListItem` object, waaraan een weergavetekst en een waarde moeten doorgegeven worden. In dit voorbeeld voegen we drie items toe aan de keuzelijst met invoervak.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Stap 4: Voeg de StructuredDocumentTag toe aan het document
 Voeg het inhoudsbesturingselement voor de keuzelijst met invoervak toe aan de hoofdtekst van het document met behulp van de`AppendChild` methode van de hoofdtekst van de eerste sectie van het document.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Stap 5: Bewaar het document
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Voorbeeldbroncode voor Combo Box Content Control met behulp van Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Dat is het! U hebt met succes een Combo Box Content Control in uw Word-document gemaakt met Aspose.Words voor .NET.