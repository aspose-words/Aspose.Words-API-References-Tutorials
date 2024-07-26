---
title: Wijzig inhoudsbesturingselementen
linktitle: Wijzig inhoudsbesturingselementen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tekst, vervolgkeuzelijsten en afbeeldingen binnen inhoudsbesturingselementen in een Word-document kunt wijzigen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/modify-content-controls/
---

In deze zelfstudie wordt uitgelegd hoe u verschillende soorten inhoudsbesturingselementen in een Word-document kunt wijzigen met Aspose.Words voor .NET. U kunt de tekst, de geselecteerde waarde van een vervolgkeuzelijst bijwerken of een afbeelding vervangen binnen de inhoudsbesturingselementen.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document en herhaal de inhoudsbesturingselementen
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Herhaal alle gestructureerde documenttags in het document met behulp van a`foreach` lus.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Voer acties uit op basis van het type inhoudscontrole
}
```

## Stap 3: Wijzig inhoudsbeheer voor platte tekst
 Voor inhoudsbesturingselementen van het type`SdtType.PlainText`, verwijder alle bestaande onderliggende alinea's, maak een nieuwe alinea en voeg een run toe met de gewenste tekst.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Stap 4: Wijzig het inhoudsbeheer van de vervolgkeuzelijst
 Voor inhoudsbesturingselementen van het type`SdtType.DropDownList` , werkt u de geselecteerde waarde bij door deze in te stellen op een specifieke waarde`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Stap 5: Wijzig het beeldinhoudsbeheer
 Voor inhoudsbesturingselementen van het type`SdtType.Picture`, haal de vorm binnen het inhoudsbesturingselement op en vervang de afbeelding door een nieuwe.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Stap 6: Sla het gewijzigde document op
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Voorbeeldbroncode voor het wijzigen van inhoudsbesturingselementen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Dat is het! U hebt met succes verschillende soorten inhoudsbesturingselementen in uw Word-document gewijzigd met Aspose.Words voor .NET.