---
title: Inhoudscontrole voor rijke tekstvakken
linktitle: Inhoudscontrole voor rijke tekstvakken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een inhoudsbesturingselement voor een RTF-vak kunt maken in een Word-document met behulp van Aspose.Words voor .NET, waardoor tekstopmaak en -stijl mogelijk wordt gemaakt.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/rich-text-box-content-control/
---

In deze zelfstudie wordt gedemonstreerd hoe u een inhoudsbesturingselement voor een RTF-vak kunt maken in een Word-document met behulp van Aspose.Words voor .NET. Met besturingselementen voor de inhoud van rich-text-vakken kunnen gebruikers tekst invoeren en opmaken met verschillende stijlen en opmaakopties.

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
 Maak een nieuw exemplaar van de`Document` klasse en een`StructuredDocumentTag` om het inhoudsbesturingselement voor het RTF-vak weer te geven. Specificeer`SdtType.RichText` als het type en`MarkupLevel.Block` als opmaakniveau om een rich-text-vak op blokniveau te maken.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Stap 3: Creëer en formatteer de Rich Text-inhoud
Maak een alinea en voer deze uit om de rich-text-inhoud weer te geven. Stel de tekst- en opmaakopties in, zoals kleur, lettertype, enz.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Stap 4: Voeg de Rich Text-inhoud toe aan het inhoudsbesturingselement
 Voeg de alinea met de rich-text-inhoud toe aan het`ChildNodes` verzameling van het inhoudsbesturingselement voor het rijke tekstvak.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Stap 5: Voeg het inhoudsbesturingselement toe aan het document
 Voeg het inhoudsbesturingselement voor het RTF-vak toe aan de hoofdtekst van het document met behulp van de`AppendChild` methode van de hoofdtekst van de eerste sectie van het document.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Stap 6: Sla het document op
 Sla het document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Voorbeeldbroncode voor Rich Text Box Content Control met behulp van Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Dat is het! U hebt met succes een inhoudsbesturingselement voor een RTF-vak in uw Word-document gemaakt met behulp van Aspose.Words voor .NET.