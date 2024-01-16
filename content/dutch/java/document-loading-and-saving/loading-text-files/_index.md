---
title: Tekstbestanden laden met Aspose.Words voor Java
linktitle: Tekstbestanden laden met
second_title: Aspose.Words Java-documentverwerkings-API
description: Ontgrendel de kracht van Aspose.Words voor Java. Leer tekstdocumenten laden, lijsten beheren, spaties verwerken en de tekstrichting bepalen.
type: docs
weight: 13
url: /nl/java/document-loading-and-saving/loading-text-files/
---

## Inleiding tot het laden van tekstbestanden met Aspose.Words voor Java

In deze handleiding onderzoeken we hoe u tekstbestanden kunt laden met Aspose.Words voor Java en deze kunt manipuleren als Word-documenten. We behandelen verschillende aspecten, zoals het detecteren van lijsten, het omgaan met spaties en het regelen van de tekstrichting.

## Stap 1: Lijsten detecteren

Om een tekstdocument te laden en lijsten te detecteren, kunt u deze stappen volgen:

```java
// Maak een document in platte tekst in de vorm van een string met delen die als lijsten kunnen worden geïnterpreteerd.
// Bij het laden worden de eerste drie lijsten altijd gedetecteerd door Aspose.Words,
// en Lijstobjecten worden na het laden voor hen gemaakt.
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
//De vierde lijst, met witruimte tussen het lijstnummer en de inhoud van het lijstitem,
// wordt alleen als lijst gedetecteerd als "DetectNumberingWithWhitespaces" in een LoadOptions-object is ingesteld op true,
// om te voorkomen dat alinea's die beginnen met getallen, ten onrechte als lijsten worden gedetecteerd.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// Laad het document terwijl u LoadOptions als parameter toepast en verifieer het resultaat.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Deze code laat zien hoe u een tekstdocument met verschillende lijstformaten laadt en de`DetectNumberingWithWhitespaces` optie om lijsten correct te detecteren.

## Stap 2: Opties voor het omgaan met spaties

Om voorloop- en volgspaties te beheren bij het laden van een tekstdocument, kunt u de volgende code gebruiken:

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

 In dit voorbeeld laden we een tekstdocument en knippen voorloop- en volgspaties af met behulp van`TxtLeadingSpacesOptions.TRIM` En`TxtTrailingSpacesOptions.TRIM`.

## Stap 3: Tekstrichting regelen

Om de tekstrichting te specificeren bij het laden van een tekstdocument, kunt u de volgende code gebruiken:

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

Deze code stelt de documentrichting in op automatische detectie (`DocumentDirection.AUTO`en laadt een tekstdocument met Hebreeuwse tekst. U kunt de documentrichting indien nodig aanpassen.

## Volledige broncode voor het laden van tekstbestanden met Aspose.Words voor Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// Maak een document in platte tekst in de vorm van een string met delen die als lijsten kunnen worden geïnterpreteerd.
	// Bij het laden worden de eerste drie lijsten altijd gedetecteerd door Aspose.Words,
	// en Lijstobjecten worden na het laden voor hen gemaakt.
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// De vierde lijst, met witruimte tussen het lijstnummer en de inhoud van het lijstitem,
	// wordt alleen als lijst gedetecteerd als "DetectNumberingWithWhitespaces" in een LoadOptions-object is ingesteld op true,
	// om te voorkomen dat alinea's die beginnen met getallen, ten onrechte als lijsten worden gedetecteerd.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// Laad het document terwijl u LoadOptions als parameter toepast en verifieer het resultaat.
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## Conclusie

In deze handleiding hebben we onderzocht hoe u tekstbestanden kunt laden met Aspose.Words voor Java, lijsten kunt detecteren, met spaties kunt omgaan en de tekstrichting kunt bepalen. Met deze technieken kunt u tekstdocumenten effectief manipuleren in uw Java-toepassingen.

## Veelgestelde vragen

### Wat is Aspose.Words voor Java?

Aspose.Words voor Java is een krachtige bibliotheek voor documentverwerking waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en converteren in Java-toepassingen. Het biedt een breed scala aan functies voor het werken met tekst, tabellen, afbeeldingen en andere documentelementen.

### Hoe kan ik aan de slag gaan met Aspose.Words voor Java?

Volg deze stappen om aan de slag te gaan met Aspose.Words voor Java:
1. Download en installeer de Aspose.Words voor Java-bibliotheek.
2.  Raadpleeg de documentatie op[Aspose.Words voor Java API-referentie](https://reference.aspose.com/words/java/)voor gedetailleerde informatie en voorbeelden.
3. Bekijk de voorbeeldcode en tutorials om te leren hoe u de bibliotheek effectief kunt gebruiken.

### Hoe laad ik een tekstdocument met Aspose.Words voor Java?

 Om een tekstdocument te laden met Aspose.Words voor Java, kunt u de`TxtLoadOptions` klasse en de`Document` klas. Zorg ervoor dat u indien nodig de juiste opties opgeeft voor het omgaan met spaties en tekstrichting. Raadpleeg de stapsgewijze handleiding in dit artikel voor een gedetailleerd voorbeeld.

### Kan ik een geladen tekstdocument naar andere formaten converteren?

 Ja, met Aspose.Words voor Java kunt u een geladen tekstdocument naar verschillende formaten converteren, waaronder DOCX, PDF en meer. U kunt gebruik maken van de`Document` klasse om conversies uit te voeren. Raadpleeg de documentatie voor specifieke conversievoorbeelden.

### Hoe ga ik om met spaties in geladen tekstdocumenten?

 U kunt bepalen hoe voorloop- en volgspaties in geladen tekstdocumenten worden verwerkt met behulp van`TxtLoadOptions` . Opties zoals`TxtLeadingSpacesOptions` En`TxtTrailingSpacesOptions`Hiermee kunt u ruimtes indien nodig inkorten of behouden. Raadpleeg het gedeelte "Opties voor omgaan met spaties" in deze handleiding voor een voorbeeld.

### Wat is de betekenis van tekstrichting in Aspose.Words voor Java?

Tekstrichting is essentieel voor documenten die gemengde scripts of talen bevatten, zoals Hebreeuws of Arabisch. Aspose.Words voor Java biedt opties om de tekstrichting te specificeren, waardoor de juiste weergave en opmaak van tekst in deze talen wordt gegarandeerd. In het gedeelte 'Tekstrichting regelen' in deze handleiding wordt gedemonstreerd hoe u de tekstrichting instelt.

### Waar kan ik meer bronnen en ondersteuning vinden voor Aspose.Words voor Java?

 Voor aanvullende bronnen, documentatie en ondersteuning gaat u naar de[Aspose.Words voor Java-documentatie](https://reference.aspose.com/words/java/). U kunt ook deelnemen aan de Aspose.Words-communityforums of contact opnemen met Aspose-ondersteuning voor hulp bij specifieke problemen of vragen.

### Is Aspose.Words voor Java geschikt voor commerciële projecten?

Ja, Aspose.Words voor Java is geschikt voor zowel persoonlijke als commerciële projecten. Het biedt licentieopties voor verschillende gebruiksscenario's. Zorg ervoor dat u de licentievoorwaarden en prijzen op de Aspose-website leest om de juiste licentie voor uw project te kiezen.