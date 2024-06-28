---
title: दस्तावेज़ों में पैराग्राफ़ और टेक्स्ट को स्टाइल करना
linktitle: दस्तावेज़ों में पैराग्राफ़ और टेक्स्ट को स्टाइल करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों में पैराग्राफ और टेक्स्ट को स्टाइल करना सीखें। प्रभावी दस्तावेज़ फ़ॉर्मेटिंग के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 11
url: /hi/java/document-styling/styling-paragraphs-text/
---
## परिचय

जब जावा में दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करने और फ़ॉर्मेट करने की बात आती है, तो जावा के लिए Aspose.Words डेवलपर्स के बीच एक शीर्ष विकल्प है। यह शक्तिशाली एपीआई आपको अपने दस्तावेज़ों में पैराग्राफ और टेक्स्ट को आसानी से बनाने, संपादित करने और स्टाइल करने की अनुमति देता है। इस व्यापक गाइड में, हम आपको जावा के लिए Aspose.Words का उपयोग करके पैराग्राफ और टेक्स्ट को स्टाइल करने की प्रक्रिया के बारे में बताएंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, स्रोत कोड के साथ यह चरण-दर-चरण मार्गदर्शिका आपको दस्तावेज़ स्वरूपण में महारत हासिल करने के लिए आवश्यक ज्ञान और कौशल से लैस करेगी। आइए गोता लगाएँ!

## जावा के लिए Aspose.Words को समझना

Aspose.Words for Java एक जावा लाइब्रेरी है जो डेवलपर्स को Microsoft Word की आवश्यकता के बिना Word दस्तावेज़ों के साथ काम करने में सक्षम बनाती है। यह दस्तावेज़ निर्माण, हेरफेर और स्वरूपण के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। जावा के लिए Aspose.Words के साथ, आप रिपोर्ट, चालान, अनुबंध और बहुत कुछ की पीढ़ी को स्वचालित कर सकते हैं, जिससे यह व्यवसायों और डेवलपर्स के लिए एक अमूल्य उपकरण बन जाता है।

## अपना विकास परिवेश स्थापित करना

इससे पहले कि हम कोडिंग पहलुओं पर गौर करें, अपना विकास वातावरण स्थापित करना महत्वपूर्ण है। सुनिश्चित करें कि आपके पास जावा स्थापित है, और फिर जावा लाइब्रेरी के लिए Aspose.Words को डाउनलोड और कॉन्फ़िगर करें। आप विस्तृत इंस्टालेशन निर्देश यहां पा सकते हैं[प्रलेखन](https://reference.aspose.com/words/java/).

## एक नया दस्तावेज़ बनाना

आइए Java के लिए Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाकर शुरुआत करें। आरंभ करने के लिए नीचे एक सरल कोड स्निपेट दिया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// दस्तावेज़ सहेजें
doc.save("NewDocument.docx");
```

यह कोड एक रिक्त Word दस्तावेज़ बनाता है और इसे "NewDocument.docx" के रूप में सहेजता है। आप सामग्री और फ़ॉर्मेटिंग जोड़कर दस्तावेज़ को और अधिक अनुकूलित कर सकते हैं।

## पैराग्राफ जोड़ना और फ़ॉर्मेट करना

पैराग्राफ किसी भी दस्तावेज़ के निर्माण खंड हैं। आप पैराग्राफ जोड़ सकते हैं और आवश्यकतानुसार उन्हें प्रारूपित कर सकते हैं। यहां पैराग्राफ जोड़ने और उनका संरेखण सेट करने का एक उदाहरण दिया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// पैराग्राफ का संरेखण सेट करें
para.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);

// पैराग्राफ में टेक्स्ट जोड़ें
Run run = new Run(doc, "This is a centered paragraph.");
para.appendChild(run);

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("FormattedDocument.docx");
```

यह कोड स्निपेट "यह एक केंद्रित पैराग्राफ है" टेक्स्ट के साथ एक केंद्रित पैराग्राफ बनाता है। वांछित स्वरूपण प्राप्त करने के लिए आप फ़ॉन्ट, रंग और बहुत कुछ अनुकूलित कर सकते हैं।

## अनुच्छेदों के भीतर पाठ को स्टाइल करना

अनुच्छेदों के भीतर अलग-अलग पाठ को प्रारूपित करना एक सामान्य आवश्यकता है। जावा के लिए Aspose.Words आपको टेक्स्ट को आसानी से स्टाइल करने की अनुमति देता है। यहां टेक्स्ट का फ़ॉन्ट और रंग बदलने का एक उदाहरण दिया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// भिन्न स्वरूपण के साथ पाठ जोड़ें
Run run = new Run(doc, "This is ");
run.getFont().setName("Arial");
run.getFont().setSize(14);
para.appendChild(run);

Run coloredRun = new Run(doc, "colored text.");
coloredRun.getFont().setColor(Color.RED);
para.appendChild(coloredRun);

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("StyledTextDocument.docx");
```

इस उदाहरण में, हम टेक्स्ट के साथ एक पैराग्राफ बनाते हैं, और फिर हम फ़ॉन्ट और रंग बदलकर टेक्स्ट के एक हिस्से को अलग तरह से स्टाइल करते हैं।

## शैलियाँ लागू करना और फ़ॉर्मेटिंग

जावा के लिए Aspose.Words पूर्वनिर्धारित शैलियाँ प्रदान करता है जिन्हें आप पैराग्राफ और टेक्स्ट पर लागू कर सकते हैं। यह फ़ॉर्मेटिंग प्रक्रिया को सरल बनाता है. पैराग्राफ में शैली कैसे लागू करें, यहां बताया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// पूर्वनिर्धारित शैली लागू करें
para.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);

// पैराग्राफ में टेक्स्ट जोड़ें
Run run = new Run(doc, "Heading 1 Style");
para.appendChild(run);

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("StyledDocument.docx");
```

इस कोड में, हम "शीर्षक 1" शैली को एक पैराग्राफ पर लागू करते हैं, जो इसे पूर्वनिर्धारित शैली के अनुसार स्वचालित रूप से प्रारूपित करता है।

## फ़ॉन्ट और रंगों के साथ कार्य करना

पाठ की उपस्थिति को ठीक करने में अक्सर फ़ॉन्ट और रंगों को संशोधित करना शामिल होता है। जावा के लिए Aspose.Words फ़ॉन्ट और रंग प्रबंधन के लिए व्यापक विकल्प प्रदान करता है। यहां फ़ॉन्ट आकार और रंग बदलने का एक उदाहरण दिया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// कस्टम फ़ॉन्ट आकार और रंग के साथ टेक्स्ट जोड़ें
Run run = new Run(doc, "Customized Text");
run.getFont().setSize(18); // फ़ॉन्ट आकार को 18 बिंदुओं पर सेट करें
run.getFont().setColor(Color.BLUE); // टेक्स्ट का रंग नीला पर सेट करें

para.appendChild(run);

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("FontAndColorDocument.docx");
```

इस कोड में, हम पैराग्राफ के भीतर टेक्स्ट के फ़ॉन्ट आकार और रंग को कस्टमाइज़ करते हैं।

## संरेखण और रिक्ति का प्रबंधन

दस्तावेज़ लेआउट के लिए पैराग्राफ और पाठ के संरेखण और रिक्ति को नियंत्रित करना आवश्यक है। यहां बताया गया है कि आप संरेखण और रिक्ति को कैसे समायोजित कर सकते हैं:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// अनुच्छेद संरेखण सेट करें
para.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);

// रिक्ति के साथ पाठ जोड़ें
Run run = new Run(doc, "Right-aligned text with spacing.");
para.appendChild(run);

// पैराग्राफ के पहले और बाद में रिक्ति जोड़ें
para.getParagraphFormat().setSpaceBefore(10); // 10 अंक पहले
para.getParagraphFormat().setSpaceAfter(10);  // 10 अंक बाद

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("AlignmentAndSpacingDocument.docx");
```

इस उदाहरण में, हम पैराग्राफ का संरेखण निर्धारित करते हैं

 दाएँ संरेखित करें और पैराग्राफ़ के पहले और बाद में रिक्तियाँ जोड़ें।

## सूचियाँ और बुलेट संभालना

बुलेट या क्रमांकन के साथ सूचियाँ बनाना एक सामान्य दस्तावेज़ स्वरूपण कार्य है। जावा के लिए Aspose.Words इसे सरल बनाता है। यहां बुलेटेड सूची बनाने का तरीका बताया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक सूची बनाएं
List list = new List(doc);

// गोलियों के साथ सूची आइटम जोड़ें
list.getListFormat().setListType(ListTemplateType.BULLET_DEFAULT);
list.getListFormat().setListLevelNumber(0);

list.appendChild(new ListItem(doc, "Item 1"));
list.appendChild(new ListItem(doc, "Item 2"));
list.appendChild(new ListItem(doc, "Item 3"));

// दस्तावेज़ में सूची जोड़ें
doc.getFirstSection().getBody().appendChild(list);

// दस्तावेज़ सहेजें
doc.save("BulletedListDocument.docx");
```

इस कोड में, हम तीन आइटमों के साथ एक बुलेटेड सूची बनाते हैं।

## हाइपरलिंक सम्मिलित करना

हाइपरलिंक आपके दस्तावेज़ों में अन्तरक्रियाशीलता जोड़ने के लिए आवश्यक हैं। जावा के लिए Aspose.Words आपको आसानी से हाइपरलिंक डालने की अनुमति देता है। यहाँ एक उदाहरण है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// एक हाइपरलिंक बनाएं
Hyperlink link = new Hyperlink(doc);
link.setAddress("https://www.example.com");
link.appendChild(new Run(doc, "Visit Example.com"));

para.appendChild(link);

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("HyperlinkDocument.docx");
```

यह कोड "https://www.example.com" पर "Example.com पर जाएँ" टेक्स्ट के साथ एक हाइपरलिंक सम्मिलित करता है।

## छवियाँ और आकृतियाँ जोड़ना

दस्तावेज़ों में अक्सर छवियों और आकृतियों जैसे दृश्य तत्वों की आवश्यकता होती है। जावा के लिए Aspose.Words आपको छवियों और आकृतियों को निर्बाध रूप से सम्मिलित करने में सक्षम बनाता है। यहां छवि जोड़ने का तरीका बताया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// एक अनुच्छेद बनाएं
Paragraph para = new Paragraph(doc);

// किसी फ़ाइल से एक छवि लोड करें
Shape image = new Shape(doc, ShapeType.IMAGE);
image.getImageData().setImage("path/to/your/image.png");

para.appendChild(image);

// दस्तावेज़ में अनुच्छेद जोड़ें
doc.getFirstSection().getBody().appendChild(para);

// दस्तावेज़ सहेजें
doc.save("ImageDocument.docx");
```

इस कोड में, हम एक फ़ाइल से एक छवि लोड करते हैं और उसे दस्तावेज़ में डालते हैं।

## पेज लेआउट और मार्जिन

वांछित स्वरूप प्राप्त करने के लिए अपने दस्तावेज़ के पृष्ठ लेआउट और मार्जिन को नियंत्रित करना महत्वपूर्ण है। यहां पेज मार्जिन सेट करने का तरीका बताया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// पेज मार्जिन सेट करें (अंकों में)
PageSetup pageSetup = doc.getFirstSection().getPageSetup();
pageSetup.setLeftMargin(72);   // 1 इंच (72 अंक)
pageSetup.setRightMargin(72);  // 1 इंच (72 अंक)
pageSetup.setTopMargin(72);    // 1 इंच (72 अंक)
pageSetup.setBottomMargin(72); // 1 इंच (72 अंक)

// दस्तावेज़ में सामग्री जोड़ें
// ...

// दस्तावेज़ सहेजें
doc.save("PageLayoutDocument.docx");
```

इस उदाहरण में, हम पृष्ठ के सभी किनारों पर 1 इंच का समान मार्जिन सेट करते हैं।

## शीर्षक और पृष्ठांक

आपके दस्तावेज़ के प्रत्येक पृष्ठ पर सुसंगत जानकारी जोड़ने के लिए शीर्षलेख और पादलेख आवश्यक हैं। यहां शीर्षलेख और पादलेख के साथ काम करने का तरीका बताया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// पहले अनुभाग के शीर्षलेख और पादलेख तक पहुँचें
HeaderFooter header = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_PRIMARY);
HeaderFooter footer = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// हेडर में सामग्री जोड़ें
Run headerRun = new Run(doc, "Header Text");
header.appendChild(headerRun);

// पाद लेख में सामग्री जोड़ें
Run footerRun = new Run(doc, "Page Number: ");
footer.appendChild(footerRun);
Field pageField = new Field(doc, FieldType.FIELD_PAGE);
footer.appendChild(pageField);

// दस्तावेज़ के मुख्य भाग में सामग्री जोड़ें
// ...

// दस्तावेज़ सहेजें
doc.save("HeaderFooterDocument.docx");
```

इस कोड में, हम दस्तावेज़ के शीर्षलेख और पादलेख दोनों में सामग्री जोड़ते हैं।

## तालिकाओं के साथ कार्य करना

तालिकाएँ आपके दस्तावेज़ों में डेटा को व्यवस्थित और प्रस्तुत करने का एक शक्तिशाली तरीका है। जावा के लिए Aspose.Words तालिकाओं के साथ काम करने के लिए व्यापक समर्थन प्रदान करता है। यहां तालिका बनाने का एक उदाहरण दिया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// 3 पंक्तियों और 3 स्तंभों वाली एक तालिका बनाएं।
Table table = new Table(doc);
table.ensureMinimum();
table.getRows().add(new Row(doc));
table.getRows().add(new Row(doc));
table.getRows().add(new Row(doc));

// तालिका कक्षों में सामग्री जोड़ें
table.getFirstRow().getCells().get(0).appendChild(new Paragraph(doc, "Row 1, Cell 1"));
table.getFirstRow().getCells().get(1).appendChild(new Paragraph(doc, "Row 1, Cell 2"));
table.getFirstRow().getCells().get(2).appendChild(new Paragraph(doc, "Row 1, Cell 3"));

//दस्तावेज़ में तालिका जोड़ें
doc.getFirstSection().getBody().appendChild(table);

// दस्तावेज़ सहेजें
doc.save("TableDocument.docx");
```

इस कोड में, हम तीन पंक्तियों और तीन स्तंभों वाली एक सरल तालिका बनाते हैं।

## दस्तावेज़ सहेजना और निर्यात करना

एक बार जब आप अपना दस्तावेज़ बना और प्रारूपित कर लें, तो उसे अपने इच्छित प्रारूप में सहेजना या निर्यात करना आवश्यक है। जावा के लिए Aspose.Words DOCX, PDF और अन्य सहित विभिन्न दस्तावेज़ प्रारूपों का समर्थन करता है। किसी दस्तावेज़ को PDF के रूप में सहेजने का तरीका यहां बताया गया है:

```java
// एक नया दस्तावेज़ बनाएँ
Document doc = new Document();

// दस्तावेज़ में सामग्री जोड़ें
// ...

// दस्तावेज़ को पीडीएफ के रूप में सहेजें
doc.save("Document.pdf", SaveFormat.PDF);
```

यह कोड स्निपेट दस्तावेज़ को पीडीएफ फ़ाइल के रूप में सहेजता है।

## उन्नत विशेषताएँ

जावा के लिए Aspose.Words जटिल दस्तावेज़ हेरफेर के लिए उन्नत सुविधाएँ प्रदान करता है। इनमें मेल मर्ज, दस्तावेज़ तुलना और बहुत कुछ शामिल हैं। इन उन्नत विषयों पर गहन मार्गदर्शन के लिए दस्तावेज़ देखें।

## युक्तियाँ और सर्वोत्तम प्रथाएँ

- आसान रखरखाव के लिए अपने कोड को मॉड्यूलर और सुव्यवस्थित रखें।
- जटिल तर्क समझाने और कोड पठनीयता में सुधार करने के लिए टिप्पणियों का उपयोग करें।
- अपडेट और अतिरिक्त संसाधनों के लिए नियमित रूप से Aspose.Words for Java दस्तावेज़ देखें।

## सामान्य समस्याओं का निवारण

Java के लिए Aspose.Words के साथ काम करते समय किसी समस्या का सामना करना पड़ा? सामान्य समस्याओं के समाधान के लिए सहायता फ़ोरम और दस्तावेज़ीकरण की जाँच करें।

## अक्सर पूछे जाने वाले प्रश्न (एफएक्यू)

### मैं अपने दस्तावेज़ में पेज ब्रेक कैसे जोड़ूँ?
अपने दस्तावेज़ में पेज ब्रेक जोड़ने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// एक पेज ब्रेक डालें
builder.insertBreak(BreakType.PAGE_BREAK);

// दस्तावेज़ में सामग्री जोड़ना जारी रखें
```

### क्या मैं Java के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को PDF में परिवर्तित कर सकता हूँ?
हां, आप जावा के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को आसानी से पीडीएफ में परिवर्तित कर सकते हैं। यहाँ एक उदाहरण है:

```java
Document doc = new Document("input.docx");
doc.save("output.pdf", SaveFormat.PDF);
```

### मैं टेक्स्ट को इस रूप में कैसे प्रारूपित करूं?

 बोल्ड या इटैलिक?
टेक्स्ट को बोल्ड या इटैलिक के रूप में प्रारूपित करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Run run = new Run(doc, "Bold and Italic Text");
run.getFont().setBold(true);    // टेक्स्ट को बोल्ड बनाएं
run.getFont().setItalic(true);  // टेक्स्ट को इटैलिक बनाएं
```

### जावा के लिए Aspose.Words का नवीनतम संस्करण क्या है?
आप जावा के लिए Aspose.Words के नवीनतम संस्करण के लिए Aspose वेबसाइट या Maven रिपॉजिटरी की जांच कर सकते हैं।

### क्या जावा के लिए Aspose.Words जावा 11 के साथ संगत है?
हां, जावा के लिए Aspose.Words जावा 11 और बाद के संस्करणों के साथ संगत है।

### मैं अपने दस्तावेज़ के विशिष्ट अनुभागों के लिए पेज मार्जिन कैसे सेट कर सकता हूँ?
आप इसका उपयोग करके अपने दस्तावेज़ के विशिष्ट अनुभागों के लिए पेज मार्जिन सेट कर सकते हैं`PageSetup` कक्षा। यहाँ एक उदाहरण है:

```java
Section section = doc.getSections().get(0); // पहला खंड प्राप्त करें
PageSetup pageSetup = section.getPageSetup();
pageSetup.setLeftMargin(72);   // अंकों में बायां मार्जिन
pageSetup.setRightMargin(72);  // अंकों में सही मार्जिन
pageSetup.setTopMargin(72);    // अंकों में शीर्ष मार्जिन
pageSetup.setBottomMargin(72); // अंकों में निचला अंतर
```

## निष्कर्ष

इस व्यापक गाइड में, हमने दस्तावेज़ों में पैराग्राफ और टेक्स्ट को स्टाइल करने के लिए जावा के लिए Aspose.Words की शक्तिशाली क्षमताओं का पता लगाया है। आपने बुनियादी पाठ हेरफेर से लेकर उन्नत सुविधाओं तक, अपने दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाना, प्रारूपित करना और बढ़ाना सीख लिया है। जावा के लिए Aspose.Words डेवलपर्स को दस्तावेज़ स्वरूपण कार्यों को कुशलतापूर्वक स्वचालित करने का अधिकार देता है। जावा के लिए Aspose.Words के साथ दस्तावेज़ स्टाइलिंग में कुशल बनने के लिए विभिन्न सुविधाओं के साथ अभ्यास और प्रयोग करते रहें।

अब जब आपको जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों में पैराग्राफ और टेक्स्ट को स्टाइल करने की ठोस समझ हो गई है, तो आप अपनी विशिष्ट आवश्यकताओं के अनुरूप खूबसूरती से स्वरूपित दस्तावेज़ बनाने के लिए तैयार हैं। हैप्पी कोडिंग!