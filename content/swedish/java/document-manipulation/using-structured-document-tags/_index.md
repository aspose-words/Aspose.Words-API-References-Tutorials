---
title: Använda SDT (Structured Document Tags) i Aspose.Words för Java
linktitle: Använda strukturerade dokumenttaggar (SDT)
second_title: Aspose.Words Java Document Processing API
description: Lär dig hur du använder Structured Document Tags (SDT) i Aspose.Words för Java med den här omfattande guiden. Skapa, modifiera och bind SDT till anpassade XML-data.
type: docs
weight: 19
url: /sv/java/document-manipulation/using-structured-document-tags/
---

## Introduktion till att använda strukturerade dokumenttaggar (SDT) i Aspose.Words för Java

Structured Document Tags (SDT) är en kraftfull funktion i Aspose.Words för Java som låter dig skapa och manipulera strukturerat innehåll i dina dokument. I den här omfattande guiden går vi igenom de olika aspekterna av att använda SDT i Aspose.Words för Java. Oavsett om du är nybörjare eller erfaren utvecklare hittar du värdefulla insikter och praktiska exempel i den här artikeln.

## Komma igång

Innan vi dyker in i detaljerna, låt oss ställa in vår miljö och skapa en grundläggande SDT. I det här avsnittet kommer vi att täcka följande ämnen:

- Skapa ett nytt dokument
- Lägga till en strukturerad dokumenttagg
- Sparar dokumentet

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en strukturerad dokumenttagg av typen CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Spara dokumentet
doc.save("WorkingWithSDT.docx");
```

## Kontrollera det aktuella tillståndet för en kryssruta SDT

När du har lagt till en kryssruta SDT i ditt dokument kanske du vill kontrollera dess aktuella tillstånd programmatiskt. Detta kan vara användbart när du behöver validera användarinmatning eller utföra specifika åtgärder baserat på kryssrutans tillstånd.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Kryssrutan är markerad
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Ändra innehållskontroller

I det här avsnittet kommer vi att utforska hur du ändrar innehållskontroller i ditt dokument. Vi kommer att täcka tre typer av innehållskontroller: vanlig text, listruta och bild.

### Ändra innehållskontroll för vanlig text

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Rensa det befintliga innehållet
    sdtPlainText.removeAllChildren();

    // Lägg till ny text
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Ändra innehållskontroll i rullgardinsmenyn

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Välj det andra objektet från listan
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Ändra bildinnehållskontroll

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Byt ut bilden mot en ny
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Skapa en ComboBox-innehållskontroll

En ComboBox Content Control låter användare välja från en fördefinierad lista med alternativ. Låt oss skapa en i vårt dokument.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Arbeta med Rich Text Content Control

Rich Text Content Controls är perfekta för att lägga till formaterad text till dina dokument. Låt oss skapa en och ställa in dess innehåll.

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

## Ställa in innehållskontrollstilar

Du kan använda stilar på innehållskontroller för att förbättra dokumentets visuella utseende. Låt oss se hur du ställer in stilen för en innehållskontroll.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Använd en anpassad stil
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Bindning av en SDT till anpassade XML-data

I vissa scenarier kan du behöva binda en SDT till anpassade XML-data för dynamisk innehållsgenerering. Låt oss undersöka hur man uppnår detta.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Skapa en tabell med upprepade sektioner mappade till anpassade XML-data

Tabeller med upprepade avsnitt kan vara extremt användbara för att presentera strukturerad data. Låt oss skapa en sådan tabell och mappa den till anpassade XML-data.

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

## Arbeta med strukturerade dokumenttaggar med flera sektioner

Strukturerade dokumenttaggar kan sträcka sig över flera avsnitt i ett dokument. I det här avsnittet kommer vi att utforska hur man arbetar med multi-sektions SDT.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Slutsats

Strukturerade dokumenttaggar i Aspose.Words för Java ger ett mångsidigt sätt att hantera och formatera innehåll i dina dokument. Oavsett om du behöver skapa mallar, formulär eller dynamiska dokument erbjuder SDT:er den flexibilitet och kontroll du behöver. Genom att följa exemplen och riktlinjerna i den här artikeln kan du utnyttja kraften hos SDT för att förbättra dina dokumentbearbetningsuppgifter.

## FAQ's

### Vad är syftet med Structured Document Tags (SDT)?

Strukturerade dokumenttaggar (SDT) tjänar syftet att organisera och formatera innehåll i dokument, vilket gör det lättare att skapa mallar, formulär och strukturerade dokument.

### Hur kan jag kontrollera det aktuella tillståndet för en Checkbox SDT?

 Du kan kontrollera aktuell status för en Checkbox SDT med hjälp av`setChecked` metod, som visas i artikeln.

### Kan jag tillämpa stilar på innehållskontroller?

Ja, du kan använda stilar på innehållskontroller för att anpassa deras utseende i dokumentet.

### Är det möjligt att binda en SDT till anpassade XML-data?

Ja, du kan binda en SDT till anpassade XML-data, vilket möjliggör dynamisk innehållsgenerering och datamappning.

### Vad är repeterande avsnitt i SDT?

Upprepande sektioner i SDT:er låter dig skapa tabeller med dynamisk data, där rader kan upprepas baserat på mappade XML-data.