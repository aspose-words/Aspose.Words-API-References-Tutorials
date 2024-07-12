---
title: Gestructureerde documenttags (SDT) gebruiken in Aspose.Words voor Java
linktitle: Gestructureerde documenttags (SDT) gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u Structured Document Tags (SDT) gebruikt in Aspose.Words voor Java met deze uitgebreide handleiding. Creëer, wijzig en bind SDT's aan aangepaste XML-gegevens.
type: docs
weight: 19
url: /nl/java/document-manipulation/using-structured-document-tags/
---

## Inleiding tot het gebruik van gestructureerde documenttags (SDT) in Aspose.Words voor Java

Gestructureerde documenttags (SDT) zijn een krachtige functie in Aspose.Words voor Java waarmee u gestructureerde inhoud in uw documenten kunt creëren en manipuleren. In deze uitgebreide handleiding leiden we u door de verschillende aspecten van het gebruik van SDT's in Aspose.Words voor Java. Of je nu een beginner of een ervaren ontwikkelaar bent, in dit artikel vind je waardevolle inzichten en praktijkvoorbeelden.

## Aan de slag

Voordat we ingaan op de details, gaan we eerst onze omgeving instellen en een basis-SDT maken. In dit gedeelte behandelen we de volgende onderwerpen:

- Een nieuw document maken
- Een gestructureerde documenttag toevoegen
- Het document opslaan

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Maak een gestructureerde documenttag van het type CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Bewaar het document
doc.save("WorkingWithSDT.docx");
```

## De huidige status van een selectievakje SDT controleren

Nadat u een selectievakje SDT aan uw document heeft toegevoegd, wilt u wellicht de huidige status programmatisch controleren. Dit kan handig zijn wanneer u gebruikersinvoer moet valideren of specifieke acties moet uitvoeren op basis van de status van het selectievakje.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Het selectievakje is aangevinkt
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Inhoudsbesturingselementen wijzigen

In deze sectie onderzoeken we hoe u inhoudsbesturingselementen in uw document kunt wijzigen. We bespreken drie soorten inhoudsbesturingselementen: platte tekst, vervolgkeuzelijst en afbeelding.

### Inhoudsbeheer voor platte tekst wijzigen

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Wis de bestaande inhoud
    sdtPlainText.removeAllChildren();

    // Voeg nieuwe tekst toe
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Inhoudsbeheer van vervolgkeuzelijsten aanpassen

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Selecteer het tweede item uit de lijst
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Beeldinhoudsbeheer aanpassen

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Vervang de afbeelding door een nieuwe
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Een ComboBox-inhoudscontrole maken

Met een ComboBox Content Control kunnen gebruikers kiezen uit een vooraf gedefinieerde lijst met opties. Laten we er een maken in ons document.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Werken met Rich Text Content Control

Rich Text Content Controls zijn perfect voor het toevoegen van opgemaakte tekst aan uw documenten. Laten we er een maken en de inhoud ervan instellen.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## Stijlen voor inhoudscontrole instellen

U kunt stijlen toepassen op inhoudsbesturingselementen om de visuele weergave van uw document te verbeteren. Laten we eens kijken hoe we de stijl van een inhoudsbesturingselement kunnen instellen.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Pas een aangepaste stijl toe
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Een SDT binden aan aangepaste XML-gegevens

In sommige scenario's moet u mogelijk een SDT binden aan aangepaste XML-gegevens voor het dynamisch genereren van inhoud. Laten we onderzoeken hoe we dit kunnen bereiken.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Een tabel maken met herhalende secties die zijn toegewezen aan aangepaste XML-gegevens

Tabellen met herhalende secties kunnen uiterst nuttig zijn voor het presenteren van gestructureerde gegevens. Laten we zo'n tabel maken en deze toewijzen aan aangepaste XML-gegevens.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## Werken met gestructureerde documenttags met meerdere secties

Gestructureerde documenttags kunnen meerdere secties in een document omvatten. In deze sectie onderzoeken we hoe u met SDT's met meerdere secties kunt werken.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Conclusie

Gestructureerde documenttags in Aspose.Words voor Java bieden een veelzijdige manier om inhoud in uw documenten te beheren en op te maken. Of u nu sjablonen, formulieren of dynamische documenten moet maken, SDT's bieden de flexibiliteit en controle die u nodig heeft. Door de voorbeelden en richtlijnen in dit artikel te volgen, kunt u de kracht van SDT's benutten om uw documentverwerkingstaken te verbeteren.

## Veelgestelde vragen

### Wat is het doel van gestructureerde documenttags (SDT's)?

Gestructureerde documenttags (SDT's) dienen voor het organiseren en opmaken van inhoud in documenten, waardoor het eenvoudiger wordt om sjablonen, formulieren en gestructureerde documenten te maken.

### Hoe kan ik de huidige status van een Checkbox SDT controleren?

 U kunt de huidige status van een Checkbox SDT controleren met behulp van de`setChecked` methode, zoals aangetoond in het artikel.

### Kan ik stijlen toepassen op inhoudsbesturingselementen?

Ja, u kunt stijlen toepassen op inhoudsbesturingselementen om de weergave ervan in het document aan te passen.

### Is het mogelijk om een SDT te binden aan aangepaste XML-gegevens?

Ja, u kunt een SDT aan aangepaste XML-gegevens binden, waardoor dynamische inhoudsgeneratie en gegevenstoewijzing mogelijk zijn.

### Wat zijn herhalende secties in SDT's?

Met herhalende secties in SDT's kunt u tabellen maken met dynamische gegevens, waarbij rijen kunnen worden herhaald op basis van de toegewezen XML-gegevens.