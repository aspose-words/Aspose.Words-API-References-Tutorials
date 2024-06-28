---
title: जावा के लिए Aspose.Words में संरचित दस्तावेज़ टैग (एसडीटी) का उपयोग करना
linktitle: संरचित दस्तावेज़ टैग (एसडीटी) का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: इस व्यापक गाइड के साथ जानें कि जावा के लिए Aspose.Words में स्ट्रक्चर्ड डॉक्यूमेंट टैग (SDT) का उपयोग कैसे करें। एसडीटी को कस्टम XML डेटा से बनाएं, संशोधित करें और बाइंड करें।
type: docs
weight: 19
url: /hi/java/document-manipulation/using-structured-document-tags/
---

## जावा के लिए Aspose.Words में संरचित दस्तावेज़ टैग (एसडीटी) का उपयोग करने का परिचय

संरचित दस्तावेज़ टैग (एसडीटी) जावा के लिए Aspose.Words में एक शक्तिशाली सुविधा है जो आपको अपने दस्तावेज़ों के भीतर संरचित सामग्री बनाने और हेरफेर करने की अनुमति देता है। इस व्यापक गाइड में, हम आपको जावा के लिए Aspose.Words में SDT के उपयोग के विभिन्न पहलुओं के बारे में बताएंगे। चाहे आप शुरुआती हों या अनुभवी डेवलपर, आपको इस लेख में मूल्यवान अंतर्दृष्टि और व्यावहारिक उदाहरण मिलेंगे।

## शुरू करना

इससे पहले कि हम विवरण में उतरें, आइए अपना परिवेश स्थापित करें और एक बुनियादी एसडीटी बनाएं। इस अनुभाग में, हम निम्नलिखित विषयों को शामिल करेंगे:

- एक नया दस्तावेज़ बनाना
- एक संरचित दस्तावेज़ टैग जोड़ना
- दस्तावेज़ सहेजा जा रहा है

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// CHECKBOX प्रकार का एक संरचित दस्तावेज़ टैग बनाएं
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// दस्तावेज़ सहेजें
doc.save("WorkingWithSDT.docx");
```

## चेकबॉक्स एसडीटी की वर्तमान स्थिति की जाँच करना

एक बार जब आप अपने दस्तावेज़ में एक चेकबॉक्स एसडीटी जोड़ लेते हैं, तो हो सकता है कि आप इसकी वर्तमान स्थिति को प्रोग्रामेटिक रूप से जांचना चाहें। यह तब उपयोगी हो सकता है जब आपको उपयोगकर्ता इनपुट को सत्यापित करने या चेकबॉक्स स्थिति के आधार पर विशिष्ट क्रियाएं करने की आवश्यकता होती है।

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // चेकबॉक्स चेक किया गया है
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## सामग्री नियंत्रण संशोधित करना

इस अनुभाग में, हम यह पता लगाएंगे कि आपके दस्तावेज़ में सामग्री नियंत्रण को कैसे संशोधित किया जाए। हम तीन प्रकार के सामग्री नियंत्रणों को कवर करेंगे: सादा पाठ, ड्रॉप-डाउन सूची और चित्र।

### सादा पाठ सामग्री नियंत्रण को संशोधित करना

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // मौजूदा सामग्री साफ़ करें
    sdtPlainText.removeAllChildren();

    // नया पाठ जोड़ें
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### ड्रॉप-डाउन सूची सामग्री नियंत्रण को संशोधित करना

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // सूची से दूसरा आइटम चुनें
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### चित्र सामग्री नियंत्रण को संशोधित करना

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // छवि को एक नई छवि से बदलें
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## कॉम्बोबॉक्स सामग्री नियंत्रण बनाना

कॉम्बोबॉक्स सामग्री नियंत्रण उपयोगकर्ताओं को विकल्पों की पूर्वनिर्धारित सूची से चयन करने की अनुमति देता है। आइए अपने दस्तावेज़ में एक बनाएँ।

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## रिच टेक्स्ट सामग्री नियंत्रण के साथ कार्य करना

रिच टेक्स्ट सामग्री नियंत्रण आपके दस्तावेज़ों में स्वरूपित टेक्स्ट जोड़ने के लिए बिल्कुल उपयुक्त हैं। आइए एक बनाएं और उसकी सामग्री सेट करें।

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

## सामग्री नियंत्रण शैलियाँ सेट करना

आप अपने दस्तावेज़ के दृश्य स्वरूप को बढ़ाने के लिए सामग्री नियंत्रण में शैलियाँ लागू कर सकते हैं। आइए देखें कि सामग्री नियंत्रण की शैली कैसे सेट करें।

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//एक कस्टम शैली लागू करें
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## SDT को कस्टम XML डेटा से बाइंड करना

कुछ परिदृश्यों में, आपको गतिशील सामग्री निर्माण के लिए एसडीटी को कस्टम XML डेटा से बांधने की आवश्यकता हो सकती है। आइए जानें कि इसे कैसे हासिल किया जाए।

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## कस्टम XML डेटा पर मैप किए गए दोहराए जाने वाले अनुभागों के साथ एक तालिका बनाना

संरचित डेटा प्रस्तुत करने के लिए दोहराए जाने वाले अनुभागों वाली तालिकाएँ बेहद उपयोगी हो सकती हैं। आइए ऐसी तालिका बनाएं और इसे कस्टम XML डेटा पर मैप करें।

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

## मल्टी-सेक्शन संरचित दस्तावेज़ टैग के साथ कार्य करना

संरचित दस्तावेज़ टैग एक दस्तावेज़ में कई अनुभागों को फैला सकते हैं। इस अनुभाग में, हम यह पता लगाएंगे कि मल्टी-सेक्शन एसडीटी के साथ कैसे काम किया जाए।

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## निष्कर्ष

जावा के लिए Aspose.Words में संरचित दस्तावेज़ टैग आपके दस्तावेज़ों में सामग्री को प्रबंधित और प्रारूपित करने का एक बहुमुखी तरीका प्रदान करते हैं। चाहे आपको टेम्प्लेट, फॉर्म या गतिशील दस्तावेज़ बनाने की आवश्यकता हो, एसडीटी आपको आवश्यक लचीलापन और नियंत्रण प्रदान करते हैं। इस आलेख में दिए गए उदाहरणों और दिशानिर्देशों का पालन करके, आप अपने दस्तावेज़ प्रसंस्करण कार्यों को बढ़ाने के लिए एसडीटी की शक्ति का उपयोग कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### संरचित दस्तावेज़ टैग (एसडीटी) का उद्देश्य क्या है?

संरचित दस्तावेज़ टैग (एसडीटी) दस्तावेज़ों के भीतर सामग्री को व्यवस्थित और स्वरूपित करने के उद्देश्य को पूरा करते हैं, जिससे टेम्पलेट, फॉर्म और संरचित दस्तावेज़ बनाना आसान हो जाता है।

### मैं चेकबॉक्स एसडीटी की वर्तमान स्थिति की जांच कैसे कर सकता हूं?

 आप इसका उपयोग करके चेकबॉक्स एसडीटी की वर्तमान स्थिति की जांच कर सकते हैं`setChecked` विधि, जैसा कि लेख में दिखाया गया है।

### क्या मैं सामग्री नियंत्रण में शैलियाँ लागू कर सकता हूँ?

हां, आप दस्तावेज़ में उनकी उपस्थिति को अनुकूलित करने के लिए सामग्री नियंत्रण में शैलियाँ लागू कर सकते हैं।

### क्या एसडीटी को कस्टम एक्सएमएल डेटा से बांधना संभव है?

हां, आप एसडीटी को कस्टम एक्सएमएल डेटा से जोड़ सकते हैं, जिससे गतिशील सामग्री निर्माण और डेटा मैपिंग की अनुमति मिलती है।

### एसडीटी में दोहराए जाने वाले अनुभाग क्या हैं?

एसडीटी में दोहराए जाने वाले अनुभाग आपको गतिशील डेटा के साथ तालिकाएं बनाने की अनुमति देते हैं, जहां मैप किए गए XML डेटा के आधार पर पंक्तियों को दोहराया जा सकता है।