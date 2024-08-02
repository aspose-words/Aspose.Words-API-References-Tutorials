---
title: Wijzig inhoudsbesturingselementen
linktitle: Wijzig inhoudsbesturingselementen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u gestructureerde documenttags in Word kunt wijzigen met Aspose.Words voor .NET. Update tekst, vervolgkeuzelijsten en afbeeldingen stap voor stap.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/modify-content-controls/
---
## Invoering

Als u ooit met Word-documenten heeft gewerkt en gestructureerde inhoudsbesturingselementen (zoals platte tekst, vervolgkeuzelijsten of afbeeldingen) moet wijzigen met Aspose.Words voor .NET, bent u hier op de juiste plek! Gestructureerde documenttags (SDT's) zijn krachtige hulpmiddelen die documentautomatisering eenvoudiger en flexibeler maken. In deze zelfstudie gaan we in op hoe u deze SDT's kunt aanpassen aan uw behoeften. Of u nu tekst bijwerkt, vervolgkeuzelijsten wijzigt of afbeeldingen verwisselt: deze handleiding begeleidt u stap voor stap door het proces.

## Vereisten

Voordat we ingaan op de kern van het wijzigen van inhoudsbesturingselementen, moet u ervoor zorgen dat u over het volgende beschikt:

1.  Aspose.Words voor .NET geïnstalleerd: Zorg ervoor dat de Aspose.Words-bibliotheek is geïnstalleerd. Zo niet, dan kan dat[download het hier](https://releases.aspose.com/words/net/).

2. Basiskennis van C#: In deze tutorial wordt ervan uitgegaan dat u bekend bent met de basisconcepten van C#-programmeren.

3. Een .NET-ontwikkelomgeving: u moet een IDE zoals Visual Studio hebben ingesteld voor het uitvoeren van .NET-toepassingen.

4. Een voorbeelddocument: we gebruiken een voorbeeld van een Word-document met verschillende soorten SDT's. U kunt degene uit het voorbeeld gebruiken of uw eigen maken.

5.  Toegang tot Aspose-documentatie: Voor meer gedetailleerde informatie, bekijk de[Aspose.Words-documentatie](https://reference.aspose.com/words/net/).

## Naamruimten importeren

Om met Aspose.Words te gaan werken, moet u de relevante naamruimten in uw C#-project importeren. Zo doe je het:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Deze naamruimten geven u toegang tot de klassen en methoden die nodig zijn voor het manipuleren van gestructureerde documenttags in uw Word-documenten.

## Stap 1: Stel uw documentpad in

 Voordat u wijzigingen aanbrengt, moet u het pad naar uw document opgeven. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar uw document is opgeslagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## Stap 2: Loop door gestructureerde documenttags

 Om SDT's te wijzigen, moet u eerst alle SDT's in het document doorlopen. Dit gebeurt met behulp van de`GetChildNodes` methode om alle knooppunten van het type te verkrijgen`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Wijzig SDT's op basis van hun type
}
```

## Stap 3: Wijzig SDT's met platte tekst

Als de SDT een teksttype zonder opmaak is, kunt u de inhoud ervan vervangen. Wis eerst de bestaande inhoud en voeg vervolgens nieuwe tekst toe.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 Uitleg: Hier,`RemoveAllChildren()`wist de bestaande inhoud van de SDT. Wij maken dan een nieuwe aan`Paragraph`En`Run` object om de nieuwe tekst in te voegen.

## Stap 4: Wijzig de vervolgkeuzelijst-SDT's

 Voor vervolgkeuzelijst-SDT's kunt u het geselecteerde item wijzigen door naar de te gaan`ListItems` verzameling. Hier selecteren we het derde item in de lijst.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Uitleg: Dit codefragment selecteert het item op index 2 (derde item) uit de vervolgkeuzelijst. Pas de index aan op basis van uw behoeften.

## Stap 5: Wijzig afbeelding-SDT's

Om een afbeelding binnen een afbeelding-SDT bij te werken, kunt u de bestaande afbeelding vervangen door een nieuwe.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 Uitleg: Deze code controleert of de vorm een afbeelding bevat en vervangt deze vervolgens door een nieuwe afbeelding op`ImagesDir`.

## Stap 6: Sla uw gewijzigde document op

Nadat u alle noodzakelijke wijzigingen heeft aangebracht, slaat u het gewijzigde document op met een nieuwe naam om uw originele document intact te houden.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Uitleg: Hierdoor wordt het document opgeslagen met een nieuwe bestandsnaam, zodat u het gemakkelijk kunt onderscheiden van het origineel.

## Conclusie

Het wijzigen van inhoudsbesturingselementen in een Word-document met Aspose.Words voor .NET is eenvoudig als u eenmaal de stappen begrijpt. Of u nu tekst bijwerkt, vervolgkeuzelijsten wijzigt of afbeeldingen verwisselt, Aspose.Words biedt een robuuste API voor deze taken. Door deze zelfstudie te volgen, kunt u de gestructureerde inhoudsbesturingselementen van uw document effectief beheren en aanpassen, waardoor uw documenten dynamischer worden en op uw behoeften worden afgestemd.

## Veelgestelde vragen

1. Wat is een gestructureerde documenttag (SDT)?

SDT's zijn elementen in Word-documenten die helpen bij het beheren en opmaken van documentinhoud, zoals tekstvakken, vervolgkeuzelijsten of afbeeldingen.

2. Hoe kan ik een nieuw vervolgkeuzemenu toevoegen aan een SDT?

 Om een nieuw item toe te voegen, gebruikt u de`ListItems` eigendom en voeg een nieuwe toe`SdtListItem` naar de collectie.

3. Kan ik Aspose.Words gebruiken om SDT's uit een document te verwijderen?

Ja, u kunt SDT's verwijderen door naar de knooppunten van het document te gaan en de gewenste SDT te verwijderen.

4. Hoe ga ik om met SDT's die in andere elementen zijn genest?

 Gebruik de`GetChildNodes` methode met de juiste parameters om toegang te krijgen tot geneste SDT's.

5. Wat moet ik doen als de SDT die ik moet wijzigen niet zichtbaar is in het document?

Zorg ervoor dat de SDT niet verborgen of beschermd is. Controleer de documentinstellingen en zorg ervoor dat uw code correct gericht is op het SDT-type.


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