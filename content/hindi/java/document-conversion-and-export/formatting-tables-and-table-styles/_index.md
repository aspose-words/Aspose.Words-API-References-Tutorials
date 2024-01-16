---
title: जावा के लिए Aspose.Words में तालिकाओं और तालिका शैलियों को फ़ॉर्मेट करना
linktitle: तालिकाओं और तालिका शैलियों का स्वरूपण
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में तालिकाओं को प्रारूपित करने और तालिका शैलियों को लागू करने का तरीका जानें। प्रभावी तालिका फ़ॉर्मेटिंग के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिकाएँ देखें। Aspose.Words के साथ अपने दस्तावेज़ लेआउट को बेहतर बनाएं।
type: docs
weight: 17
url: /hi/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## जावा के लिए Aspose.Words में फ़ॉर्मेटिंग टेबल और टेबल शैलियों का परिचय

दस्तावेज़ों में जानकारी की संरचना और व्यवस्थित करने में तालिकाएँ महत्वपूर्ण भूमिका निभाती हैं। जावा के लिए Aspose.Words आपके दस्तावेज़ों की दृश्य अपील को बढ़ाने के लिए तालिकाओं को फ़ॉर्मेट करने और तालिका शैलियों को लागू करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। इस चरण-दर-चरण मार्गदर्शिका में, हम जावा के लिए Aspose.Words का उपयोग करके तालिकाओं को फ़ॉर्मेट करने और तालिका शैलियों को लागू करने के विभिन्न पहलुओं का पता लगाएंगे।

## आवश्यक शर्तें

इससे पहले कि हम विवरण में उतरें, सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Words आपके प्रोजेक्ट में एकीकृत है। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/).

## टेबल और आसपास के पाठ के बीच दूरी प्राप्त करें

आरंभ करने के लिए, आइए जानें कि किसी दस्तावेज़ में तालिका और आसपास के पाठ के बीच की दूरी कैसे प्राप्त करें।

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## किसी तालिका पर आउटलाइन बॉर्डर लागू करें

आप किसी तालिका को पृष्ठ के केंद्र में संरेखित कर सकते हैं, मौजूदा सीमाओं को साफ़ कर सकते हैं, और इस कोड के साथ एक कस्टम रूपरेखा सीमा निर्धारित कर सकते हैं:

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

## बॉर्डर वाली एक टेबल बनाएं

यह कोड स्निपेट दर्शाता है कि तालिका कैसे बनाएं और तालिका और उसकी कोशिकाओं दोनों के लिए सीमाएँ कैसे निर्धारित करें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## पंक्ति स्वरूपण संशोधित करें

जानें कि किसी तालिका के भीतर किसी विशिष्ट पंक्ति के स्वरूपण को कैसे संशोधित किया जाए:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## पंक्ति स्वरूपण लागू करें

यह उदाहरण दर्शाता है कि तालिका में संपूर्ण पंक्ति में फ़ॉर्मेटिंग कैसे लागू करें:

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

जानें कि किसी तालिका में अलग-अलग सेल के लिए पैडिंग कैसे सेट करें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## सेल फ़ॉर्मेटिंग को संशोधित करें

जानें कि किसी तालिका के भीतर किसी विशिष्ट सेल के स्वरूपण को कैसे संशोधित किया जाए:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## विभिन्न सीमाओं के साथ तालिका और सेल को प्रारूपित करें

जानें कि किसी तालिका में अलग-अलग सेल के लिए अलग-अलग बॉर्डर कैसे सेट करें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// तालिका की सीमाएँ निर्धारित करें
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// अलग-अलग सेल के लिए सेल शेडिंग सेट करें
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// कक्षों में सामग्री जोड़ें
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// अगली पंक्ति के लिए सेल फ़ॉर्मेटिंग साफ़ करें
builder.getCellFormat().clearFormatting();
// इस पंक्ति की पहली सेल के लिए बड़े बॉर्डर बनाएं
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## तालिका का शीर्षक और विवरण सेट करें

अपनी तालिका में एक शीर्षक और विवरण जोड़ें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## चरण 10: सेल स्पेसिंग की अनुमति दें

सेल रिक्ति की अनुमति दें और तालिका के लिए इसका मान निर्धारित करें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## चरण 11: स्टाइल के साथ एक टेबल बनाएं

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

## चरण 12: स्टाइल से सेल और पंक्तियों पर फ़ॉर्मेटिंग का विस्तार करें

कक्षों और पंक्तियों पर फ़ॉर्मेटिंग लागू करने के लिए तालिका शैलियों का विस्तार करना सीखें:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## चरण 13: एक टेबल स्टाइल बनाएं

विशिष्ट स्वरूपण के साथ एक कस्टम तालिका शैली बनाएं:

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

## चरण 14: सशर्त स्वरूपण को परिभाषित करें

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

अलग-अलग कोशिकाओं के लिए विशिष्ट स्वरूपण सेट करें:

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

## चरण 16: टेबलरो फ़ॉर्मेटिंग सेट करें

किसी तालिका में संपूर्ण पंक्तियों पर फ़ॉर्मेटिंग लागू करें:

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

जावा के लिए Aspose.Words आपको तालिकाओं को प्रारूपित करने और तालिका शैलियों को सटीकता के साथ लागू करने का अधिकार देता है। व्यक्तिगत सेल फ़ॉर्मेटिंग को संशोधित करने से लेकर कस्टम तालिका शैलियाँ बनाने तक, आपके पास अपने दस्तावेज़ों को आकर्षक और व्यवस्थित बनाने के लिए उपकरण हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Words कैसे डाउनलोड करूं?

 आप जावा के लिए Aspose.Words को Aspose वेबसाइट से डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/).

### क्या मैं एक तालिका के भीतर अलग-अलग कोशिकाओं पर अलग-अलग सीमाएँ लागू कर सकता हूँ?

हां, आप जावा के लिए Aspose.Words का उपयोग करके तालिका के भीतर अलग-अलग सेल के लिए अलग-अलग बॉर्डर सेट कर सकते हैं, जैसा कि इस गाइड में दिखाया गया है।

### तालिका का शीर्षक और विवरण निर्धारित करने का उद्देश्य क्या है?

तालिका का शीर्षक और विवरण सेट करने से आपके दस्तावेज़ की पहुंच और संगठन में वृद्धि होती है, जिससे पाठकों और सहायक प्रौद्योगिकियों के लिए सामग्री को समझना आसान हो जाता है।

### मैं किसी तालिका में विशिष्ट पंक्तियों पर सशर्त स्वरूपण कैसे लागू कर सकता हूँ?

आप सशर्त स्वरूपण नियमों के साथ कस्टम तालिका शैलियों को परिभाषित करके तालिका में विशिष्ट पंक्तियों पर सशर्त स्वरूपण लागू कर सकते हैं, जैसा कि इस गाइड में दिखाया गया है।

### जावा के लिए Aspose.Words के लिए मुझे अधिक दस्तावेज़ और संसाधन कहां मिल सकते हैं?

 व्यापक दस्तावेज़ीकरण और अतिरिक्त संसाधनों के लिए, कृपया जावा दस्तावेज़ीकरण के लिए Aspose.Words पर जाएँ:[जावा दस्तावेज़ीकरण के लिए Aspose.Words](https://reference.aspose.com/words/java/).