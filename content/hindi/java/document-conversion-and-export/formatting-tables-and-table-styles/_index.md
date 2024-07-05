---
title: Java के लिए Aspose.Words में तालिकाओं और तालिका शैलियों का प्रारूपण
linktitle: तालिकाओं और तालिका शैलियों का प्रारूपण
second_title: Aspose.Words जावा दस्तावेज़ प्रसंस्करण एपीआई
description: Java के लिए Aspose.Words में टेबल को फ़ॉर्मेट करना और टेबल स्टाइल लागू करना सीखें। प्रभावी टेबल फ़ॉर्मेटिंग के लिए सोर्स कोड के साथ चरण-दर-चरण गाइड देखें। Aspose.Words के साथ अपने दस्तावेज़ लेआउट को बेहतर बनाएँ।
type: docs
weight: 17
url: /hi/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## जावा के लिए Aspose.Words में तालिकाओं और तालिका शैलियों को प्रारूपित करने का परिचय

दस्तावेज़ों में जानकारी को संरचित और व्यवस्थित करने में तालिकाएँ महत्वपूर्ण भूमिका निभाती हैं। Aspose.Words for Java आपके दस्तावेज़ों की दृश्य अपील को बढ़ाने के लिए तालिकाओं को फ़ॉर्मेट करने और तालिका शैलियों को लागू करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। इस चरण-दर-चरण मार्गदर्शिका में, हम Aspose.Words for Java का उपयोग करके तालिकाओं को फ़ॉर्मेट करने और तालिका शैलियों को लागू करने के विभिन्न पहलुओं का पता लगाएँगे।

## आवश्यक शर्तें

इससे पहले कि हम विवरण में उतरें, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Words for Java लाइब्रेरी एकीकृत है। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं:[Java के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/).

## तालिका और आस-पास के पाठ के बीच की दूरी प्राप्त करें

सबसे पहले, आइए जानें कि किसी दस्तावेज़ में तालिका और उसके आस-पास के पाठ के बीच की दूरी कैसे प्राप्त करें।

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## किसी टेबल पर आउटलाइन बॉर्डर लागू करें

आप इस कोड के साथ तालिका को पृष्ठ के केंद्र में संरेखित कर सकते हैं, मौजूदा बॉर्डर साफ़ कर सकते हैं, और कस्टम आउटलाइन बॉर्डर सेट कर सकते हैं:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## बॉर्डर के साथ एक टेबल बनाएं

यह कोड स्निपेट दर्शाता है कि तालिका कैसे बनायें तथा तालिका और उसके कक्षों दोनों के लिए बॉर्डर कैसे सेट करें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## पंक्ति स्वरूपण संशोधित करें

तालिका में किसी विशिष्ट पंक्ति के स्वरूपण को संशोधित करने का तरीका जानें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## पंक्ति स्वरूपण लागू करें

यह उदाहरण दर्शाता है कि तालिका में संपूर्ण पंक्ति पर स्वरूपण कैसे लागू किया जाता है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## सेल पैडिंग सेट करें

तालिका में अलग-अलग कक्षों के लिए पैडिंग सेट करने का तरीका जानें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## सेल स्वरूपण संशोधित करें

तालिका के भीतर किसी विशिष्ट कक्ष के स्वरूपण को संशोधित करने का तरीका जानें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## टेबल और सेल को अलग-अलग बॉर्डर के साथ फ़ॉर्मेट करें

तालिका में अलग-अलग कक्षों के लिए अलग-अलग सीमाएँ निर्धारित करना सीखें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// तालिका की सीमाएँ निर्धारित करें
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// अलग-अलग कोशिकाओं के लिए सेल शेडिंग सेट करें
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// कक्षों में सामग्री जोड़ें
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// अगली पंक्ति के लिए सेल फ़ॉर्मेटिंग साफ़ करें
builder.getCellFormat().clearFormatting();
// इस पंक्ति के पहले सेल के लिए बड़ी बॉर्डर बनाएँ
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## तालिका शीर्षक और विवरण सेट करें

अपनी तालिका में शीर्षक और विवरण जोड़ें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## चरण 10: सेल स्पेसिंग की अनुमति दें

तालिका के लिए कक्ष रिक्ति की अनुमति दें और उसका मान सेट करें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## चरण 11: स्टाइल के साथ एक तालिका बनाएं

पूर्वनिर्धारित शैली के साथ एक तालिका बनाएं:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## चरण 12: स्टाइल से कक्षों और पंक्तियों पर फ़ॉर्मेटिंग का विस्तार करें

कक्षों और पंक्तियों पर स्वरूपण लागू करने के लिए तालिका शैलियों का विस्तार करना सीखें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## चरण 13: तालिका शैली बनाएँ

विशिष्ट स्वरूपण के साथ एक कस्टम तालिका शैली बनाएँ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## चरण 14: सशर्त स्वरूपण परिभाषित करें

तालिका में पंक्तियों पर सशर्त स्वरूपण लागू करें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## चरण 15: टेबलसेल फ़ॉर्मेटिंग सेट करें

अलग-अलग कक्षों के लिए विशिष्ट स्वरूपण सेट करें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## चरण 16: TableRow स्वरूपण सेट करें

तालिका में संपूर्ण पंक्तियों पर स्वरूपण लागू करें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## निष्कर्ष

Aspose.Words for Java आपको टेबल को फ़ॉर्मेट करने और सटीकता के साथ टेबल स्टाइल लागू करने की शक्ति देता है। अलग-अलग सेल फ़ॉर्मेटिंग को संशोधित करने से लेकर कस्टम टेबल स्टाइल बनाने तक, आपके पास अपने दस्तावेज़ों को आकर्षक और व्यवस्थित बनाने के लिए उपकरण हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Words कैसे डाउनलोड करूं?

 आप Aspose.Words for Java को Aspose वेबसाइट से डाउनलोड कर सकते हैं:[Java के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/).

### क्या मैं किसी तालिका के अलग-अलग कक्षों पर अलग-अलग बॉर्डर लगा सकता हूँ?

हां, आप Java के लिए Aspose.Words का उपयोग करके तालिका के भीतर अलग-अलग कक्षों के लिए अलग-अलग सीमाएं निर्धारित कर सकते हैं, जैसा कि इस गाइड में प्रदर्शित किया गया है।

### तालिका शीर्षक और विवरण सेट करने का उद्देश्य क्या है?

तालिका शीर्षक और विवरण सेट करने से आपके दस्तावेज़ की पहुंच और संगठन में वृद्धि होती है, जिससे पाठकों और सहायक प्रौद्योगिकियों के लिए सामग्री को समझना आसान हो जाता है।

### मैं किसी तालिका में विशिष्ट पंक्तियों पर सशर्त स्वरूपण कैसे लागू कर सकता हूँ?

आप सशर्त स्वरूपण नियमों के साथ कस्टम तालिका शैलियाँ परिभाषित करके तालिका में विशिष्ट पंक्तियों पर सशर्त स्वरूपण लागू कर सकते हैं, जैसा कि इस गाइड में दिखाया गया है।

### मैं Java के लिए Aspose.Words के लिए अधिक दस्तावेज़ और संसाधन कहां पा सकता हूं?

 विस्तृत दस्तावेज़ीकरण और अतिरिक्त संसाधनों के लिए, कृपया Java के लिए Aspose.Words दस्तावेज़ीकरण पर जाएँ:[जावा दस्तावेज़ीकरण के लिए Aspose.Words](https://reference.aspose.com/words/java/).