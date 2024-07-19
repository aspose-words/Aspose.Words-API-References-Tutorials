---
title: Selectievakje Type inhoudscontrole
linktitle: Selectievakje Type inhoudscontrole
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een inhoudsbesturingselement voor selectievakjes in een Word-document kunt maken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/check-box-type-content-control/
---

In deze zelfstudie wordt uitgelegd hoe u een inhoudsbesturingselement voor selectievakjes in een Word-document kunt maken met Aspose.Words voor .NET. Met besturingselementen voor de inhoud van selectievakjes kunnen gebruikers een selectievakje in het document in- of uitschakelen.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"`met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` om de inhoud van het document op te bouwen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een inhoudsbesturingselement voor selectievakjes toe
 Maak een`StructuredDocumentTag` met`SdtType.Checkbox` om het inhoudsbesturingselement voor het selectievakje weer te geven. Specificeer`MarkupLevel.Inline` om het in de tekst te plaatsen.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Stap 4: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Voorbeeldbroncode voor Check Box Type Content Control met behulp van Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Dat is het! U hebt met succes een inhoudsbesturingselement voor selectievakjes in uw Word-document gemaakt met Aspose.Words voor .NET.