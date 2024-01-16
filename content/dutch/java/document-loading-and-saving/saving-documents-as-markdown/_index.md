---
title: Documenten opslaan als Markdown in Aspose.Words voor Java
linktitle: Documenten opslaan als Markdown
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u Word-documenten naar Markdown converteert met Aspose.Words voor Java. In deze stapsgewijze handleiding wordt aandacht besteed aan het uitlijnen van tabellen, het hanteren van afbeeldingen en meer.
type: docs
weight: 18
url: /nl/java/document-loading-and-saving/saving-documents-as-markdown/
---

## Inleiding tot het opslaan van documenten als markdown in Aspose.Words voor Java

In deze stapsgewijze handleiding laten we zien hoe u documenten kunt opslaan als Markdown met behulp van Aspose.Words voor Java. Markdown is een lichtgewicht opmaaktaal die vaak wordt gebruikt voor het opmaken van tekstdocumenten. Met Aspose.Words voor Java kunt u uw Word-documenten eenvoudig converteren naar Markdown-indeling. We behandelen verschillende aspecten van het opslaan van Markdown-bestanden, inclusief het uitlijnen van tabelinhoud en het omgaan met afbeeldingen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Words voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).

## Stap 1: Een Word-document maken

Laten we beginnen met het maken van een Word-document dat we later zullen converteren naar het Markdown-formaat. U kunt dit document naar eigen wens aanpassen.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een tabel met twee cellen in
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// Sla het document op als Markdown
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 In dit voorbeeld maken we een eenvoudige tabel met twee cellen en stellen we de uitlijning van de alinea's in deze cellen in. Vervolgens slaan we het document op als Markdown met behulp van de`MarkdownSaveOptions`.

## Stap 2: Pas de uitlijning van tabelinhoud aan

Met Aspose.Words voor Java kunt u de uitlijning van tabelinhoud aanpassen wanneer u deze opslaat als Markdown. U kunt de tabelinhoud links, rechts, gecentreerd uitlijnen of automatisch laten bepalen op basis van de eerste alinea in elke tabelkolom.

U kunt als volgt de uitlijning van tabelinhoud aanpassen:

```java
// Stel de uitlijning van de tabelinhoud in op links
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// Stel de uitlijning van de tabelinhoud in op rechts
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// Stel de uitlijning van de tabelinhoud in op het midden
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//Stel de uitlijning van de tabelinhoud in op automatisch (bepaald door de eerste alinea)
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 Door het veranderen van de`TableContentAlignment` eigenschap, kunt u bepalen hoe de inhoud in tabellen wordt uitgelijnd bij het converteren naar Markdown.

## Stap 3: Afbeeldingen verwerken

 Om afbeeldingen in uw Markdown-document op te nemen, moet u de map opgeven waarin de afbeeldingen zich bevinden. Met Aspose.Words voor Java kunt u de map afbeeldingen instellen in de`MarkdownSaveOptions`.

Zo stelt u de map Afbeeldingen in en slaat u het document met afbeeldingen op:

```java
// Laad een document met afbeeldingen
Document doc = new Document("document_with_images.docx");

// Stel het mappad voor afbeeldingen in
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// Sla het document met afbeeldingen op
doc.save("document_with_images.md", saveOptions);
```

 Zorg ervoor dat u vervangt`"document_with_images.docx"` met het pad naar uw Word-document met afbeeldingen en`"images_folder/"` met het daadwerkelijke pad naar de map waarin uw afbeeldingen zijn opgeslagen.

## Volledige broncode voor het opslaan van documenten als markdown in Aspose.Words voor Java

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// Zorgt ervoor dat alle alinea's in de tabel worden uitgelijnd.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// De uitlijning wordt in dit geval overgenomen uit de eerste alinea in de overeenkomstige tabelkolom.
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## Conclusie

In deze handleiding hebben we onderzocht hoe u documenten kunt opslaan als Markdown met Aspose.Words voor Java. We hebben het maken van een Word-document besproken, het aanpassen van de uitlijning van de tabelinhoud en het verwerken van afbeeldingen in Markdown-bestanden. U kunt uw Word-documenten nu efficiënt converteren naar het Markdown-formaat, waardoor ze geschikt zijn voor verschillende publicatieplatforms en documentatiebehoeften.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Words voor Java?

 Aspose.Words voor Java kan worden geïnstalleerd door de bibliotheek in uw Java-project op te nemen. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/words/java/) en volg de installatie-instructies in de documentatie.

### Kan ik complexe Word-documenten met tabellen en afbeeldingen converteren naar Markdown?

Ja, Aspose.Words voor Java ondersteunt de conversie van complexe Word-documenten met tabellen, afbeeldingen en verschillende opmaakelementen naar Markdown. U kunt de Markdown-uitvoer aanpassen aan de complexiteit van uw document.

### Hoe kan ik omgaan met afbeeldingen in Markdown-bestanden?

 Om afbeeldingen in Markdown-bestanden op te nemen, stelt u het mappad voor afbeeldingen in met behulp van de`setImagesFolder`methode in`MarkdownSaveOptions`. Zorg ervoor dat de afbeeldingsbestanden in de opgegeven map zijn opgeslagen, en Aspose.Words voor Java zal de afbeeldingsreferenties dienovereenkomstig verwerken.

### Is er een proefversie van Aspose.Words voor Java beschikbaar?

Ja, u kunt een proefversie van Aspose.Words voor Java verkrijgen via de Aspose-website. Met de proefversie kunt u de mogelijkheden van de bibliotheek evalueren voordat u een licentie aanschaft.

### Waar kan ik meer voorbeelden en documentatie vinden?

 Voor meer voorbeelden, documentatie en gedetailleerde informatie over Aspose.Words voor Java gaat u naar de[documentatie](https://reference.aspose.com/words/java/).