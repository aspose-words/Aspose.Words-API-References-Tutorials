---
title: Word-document splitsen op kop Html
linktitle: Op rubrieken Html
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om de C#-broncode van het gesplitste woorddocument uit te leggen. By Heading HTML-functie van Aspose.Words voor .NET
type: docs
weight: 10
url: /nl/net/split-document/by-headings-html/
---
In deze zelfstudie laten we u zien hoe u een Word-document in kleinere delen kunt splitsen met behulp van de functie By HTML Heading van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en afzonderlijke HTML-documenten te genereren op basis van Heading.

## Stap 1: Het document laden

Om te beginnen geeft u de map voor uw document op en laadt u het document in een Document-object. Hier is hoe:

```csharp
//Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Stap 2: Het document verdelen op kop in HTML-formaat

Nu zullen we de opslagopties instellen om het document in kleinere delen te splitsen op basis van de kop in HTML-indeling. Hier is hoe:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Splits het document in kleinere delen, in dit geval op titel.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Voorbeeldbroncode voor By Headings HTML met Aspose.Words voor .NET

Hier is de volledige broncode voor de By HTML Heading-functie van Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Splits een document in kleinere delen, in dit geval opgesplitst per kop.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Met deze code kunt u een Word-document in kleinere delen splitsen met behulp van Aspose.Words voor .NET, op basis van kopjes. Vervolgens kunt u voor elk onderdeel afzonderlijke HTML-documenten genereren.

## Conclusie

 In deze zelfstudie hebben we geleerd hoe u een Word-document in kleinere delen kunt splitsen met behulp van de functie By HTML Heading van Aspose.Words voor .NET. Door het opgeven van de`DocumentSplitCriteria` als`HeadingParagraph` in de`HtmlSaveOptions`, konden we afzonderlijke HTML-documenten genereren op basis van de koppen in het originele document.

Het opsplitsen van een document in kopjes kan handig zijn voor het ordenen en beheren van de inhoud, vooral bij grote documenten met meerdere secties. Aspose.Words voor .NET biedt een betrouwbare en efficiënte oplossing voor het splitsen van documenten en het genereren van uitvoer in verschillende formaten.

Ontdek gerust de extra functies en opties van Aspose.Words voor .NET om uw documentverwerkingsmogelijkheden verder te verbeteren en uw workflow te stroomlijnen.

### Veelgestelde vragen

#### Hoe kan ik een Word-document opsplitsen in kleinere delen op basis van koppen met Aspose.Words voor .NET?

 Als u een Word-document wilt splitsen op basis van koppen, kunt u de functie By HTML Heading van Aspose.Words voor .NET gebruiken. Volg de meegeleverde broncode en stel de`DocumentSplitCriteria` naar`HeadingParagraph` in de`HtmlSaveOptions` voorwerp. Hierdoor wordt het document bij elke kop in kleinere delen opgesplitst.

#### In welke formaten kan ik het Word-document opsplitsen?

 De meegeleverde broncode demonstreert het opsplitsen van het Word-document in kleinere delen in HTML-formaat. Aspose.Words voor .NET ondersteunt echter verschillende uitvoerformaten, waaronder DOCX, PDF, EPUB en meer. U kunt de code wijzigen en het gewenste uitvoerformaat opgeven in het`HtmlSaveOptions` dienovereenkomstig bezwaar maken.

#### Kan ik een ander criterium kiezen voor het splitsen van het document?

Ja, u kunt een ander criterium kiezen voor het splitsen van het document op basis van uw vereisten. Aspose.Words voor .NET biedt verschillende criteria-opties, zoals`HeadingParagraph`, `Page`, `Section` , en meer. Wijzig de`DocumentSplitCriteria` eigendom in de`HtmlSaveOptions` object om de juiste criteria voor splitsing te selecteren.

#### Hoe kan ik de uitvoer-HTML voor de gesplitste delen aanpassen?

 Met Aspose.Words voor .NET kunt u de uitvoer-HTML voor de gesplitste delen aanpassen door extra opties op te geven in de`HtmlSaveOptions` voorwerp. U kunt verschillende aspecten beheren, zoals CSS-stijlen, afbeeldingen, lettertypen en meer. Raadpleeg de Aspose.Words-documentatie voor meer details over het aanpassen van de HTML-uitvoer.

#### Kan ik het document opsplitsen op basis van meerdere criteria?

 Ja, u kunt het document opsplitsen op basis van meerdere criteria door de criteria-opties dienovereenkomstig te combineren. U kunt het document bijvoorbeeld splitsen op kop en pagina door de`DocumentSplitCriteria`eigendom aan`HeadingParagraph | Page`. Hierdoor wordt het document bij elke kop en elke pagina opgesplitst, waardoor kleinere delen worden gemaakt op basis van beide criteria.