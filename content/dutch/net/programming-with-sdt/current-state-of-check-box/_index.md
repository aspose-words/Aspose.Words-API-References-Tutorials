---
title: Huidige status van het selectievakje
linktitle: Huidige status van het selectievakje
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de huidige status van een inhoudsbesturingselement voor selectievakjes in een Word-document kunt ophalen en instellen met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/current-state-of-check-box/
---

In deze zelfstudie wordt uitgelegd hoe u de huidige status van een inhoudsbesturingselement voor selectievakjes in een Word-document kunt ophalen en instellen met behulp van Aspose.Words voor .NET. U kunt het selectievakje in- of uitschakelen op basis van de huidige status.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document en haal het inhoudsbeheer van het selectievakje op
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Haal vervolgens het gewenste inhoudsbesturingselement voor selectievakjes op uit het document. In dit voorbeeld gaan we ervan uit dat het selectievakje de eerste gestructureerde documenttag in het document is.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Stap 3: Schakel het selectievakje in of uit op basis van de huidige status
 Controleer of de opgehaalde gestructureerde documenttag van het type is`SdtType.Checkbox` . Als dit het geval is, stelt u de`Checked` eigendom van het inhoudsbesturingselement`true` om het vakje aan te vinken. Anders kunt u dit uitgeschakeld laten.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Stap 4: Sla het document op
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Voorbeeldbroncode voor Current State Of Check Box met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Haal het eerste inhoudsbesturingselement uit het document.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Dat is het! U hebt met succes de huidige status van een inhoudsbesturingselement voor selectievakjes in uw Word-document opgehaald en ingesteld met Aspose.Words voor .NET.