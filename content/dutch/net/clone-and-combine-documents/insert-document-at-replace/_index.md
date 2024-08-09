---
title: Document invoegen bij vervangen
linktitle: Document invoegen bij vervangen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u naadloos het ene Word-document in het andere kunt invoegen met Aspose.Words voor .NET met onze gedetailleerde, stapsgewijze handleiding. Perfect voor ontwikkelaars die de documentverwerking willen stroomlijnen.
type: docs
weight: 10
url: /nl/net/clone-and-combine-documents/insert-document-at-replace/
---
## Invoering

Hallo daar, documentmeesters! Heb je ooit diep in de code gezeten, terwijl je probeerde uit te vinden hoe je het ene Word-document naadloos in het andere kon invoegen? Wees niet bang, want vandaag duiken we in de wereld van Aspose.Words voor .NET om die taak een fluitje van een cent te maken. We zullen een gedetailleerde, stapsgewijze handleiding doornemen over hoe u deze krachtige bibliotheek kunt gebruiken om documenten op specifieke punten in te voegen tijdens een zoek- en vervangbewerking. Klaar om een Aspose.Words-wizard te worden? Laten we beginnen!

## Vereisten

Voordat we ingaan op de code, zijn er een paar dingen die u moet regelen:

-  Visual Studio: Zorg ervoor dat Visual Studio op uw computer is geïnstalleerd. Als u deze nog niet heeft, kunt u deze downloaden via[hier](https://visualstudio.microsoft.com/).
-  Aspose.Words voor .NET: Je hebt de Aspose.Words-bibliotheek nodig. U kunt deze verkrijgen bij de[Aspose-website](https://releases.aspose.com/words/net/).
- Basiskennis van C#: Een basiskennis van C# en .NET zal u helpen deze tutorial te volgen.

Oké, nu we die uit de weg hebben, laten we onze handen vuil maken met wat code!

## Naamruimten importeren

Allereerst moeten we de benodigde naamruimten importeren om met Aspose.Words te kunnen werken. Dit is hetzelfde als het verzamelen van al uw gereedschap voordat u aan een project begint. Voeg deze toe met behulp van richtlijnen bovenaan uw C#-bestand:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Nu we de randvoorwaarden op orde hebben, gaan we het proces in hapklare stappen opsplitsen. Elke stap is cruciaal en zal ons dichter bij ons doel brengen.

## Stap 1: De documentenmap instellen

Eerst moeten we de map opgeven waar onze documenten zijn opgeslagen. Dit is hetzelfde als het voorbereiden van een grote voorstelling.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar uw directory. Dit is waar uw documenten zullen leven en ademen.

## Stap 2: Laad het hoofddocument

Vervolgens laden we het hoofddocument waarin we een ander document willen invoegen. Zie dit als ons hoofdpodium waar alle actie zal plaatsvinden.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Deze code laadt het hoofddocument uit de opgegeven map.

## Stap 3: Stel de opties voor zoeken en vervangen in

Om de specifieke locatie te vinden waar we ons document willen invoegen, gebruiken we de zoek- en vervangfunctionaliteit. Dit is hetzelfde als het gebruik van een kaart om de exacte plek voor onze nieuwe aanwinst te vinden.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Hier stellen we de richting in op achteruit en specificeren we een aangepaste callback-handler die we vervolgens zullen definiëren.

## Stap 4: Voer de vervangingsbewerking uit

Nu vertellen we ons hoofddocument dat het naar een specifieke plaatsaanduidingstekst moet zoeken en deze door niets moet vervangen, terwijl we onze aangepaste callback gebruiken om een ander document in te voegen.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Deze code voert de zoek- en vervangbewerking uit en slaat vervolgens het bijgewerkte document op.

## Stap 5: Maak een aangepaste vervangende callback-handler

Onze aangepaste callback-handler is waar de magie gebeurt. Deze handler definieert hoe het invoegen van documenten wordt uitgevoerd tijdens de zoek- en vervangbewerking.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Voeg een document in na de alinea die de matchtekst bevat.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Verwijder de alinea met de overeenkomende tekst.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Hier laden we het in te voegen document en roepen vervolgens een hulpmethode aan om de invoeging uit te voeren.

## Stap 6: Definieer de methode voor het invoegen van documenten

Het laatste stukje van onze puzzel is de methode die het document daadwerkelijk op de opgegeven locatie invoegt.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Loop door alle knooppunten op blokniveau in de hoofdtekst van de sectie,
		// kloon en voeg vervolgens elk knooppunt in dat niet de laatste lege alinea van een sectie is.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

Deze methode zorgt ervoor dat knooppunten uit het in te voegen document worden geïmporteerd en op de juiste plek in het hoofddocument worden geplaatst.

## Conclusie

En daar heb je het! Een uitgebreide handleiding voor het invoegen van het ene document in het andere met Aspose.Words voor .NET. Door deze stappen te volgen, kunt u eenvoudig de taken voor het samenstellen en manipuleren van documenten automatiseren. Of u nu een documentbeheersysteem bouwt of gewoon uw documentverwerkingsworkflow wilt stroomlijnen, Aspose.Words is uw vertrouwde hulpje.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor het programmatisch manipuleren van Word-documenten. Hiermee kunt u eenvoudig Word-documenten maken, wijzigen, converteren en verwerken.

### Kan ik meerdere documenten tegelijk invoegen?
Ja, u kunt de callback-handler aanpassen om meerdere invoegingen af te handelen door een verzameling documenten te herhalen.

### Is er een gratis proefversie beschikbaar?
 Absoluut! U kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning voor Aspose.Words?
 kunt ondersteuning krijgen door naar de[Aspose.Words-forum](https://forum.aspose.com/c/words/8).

### Kan ik de opmaak van het ingevoegde document behouden?
 Ja, de`NodeImporter` Met class kunt u opgeven hoe de opmaak wordt afgehandeld bij het importeren van knooppunten van het ene document naar het andere.