---
title: जावा के लिए Aspose.Words में दस्तावेज़ आकृतियों का उपयोग करना
linktitle: दस्तावेज़ आकृतियों का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में दस्तावेज़ आकृतियों की शक्ति को अनलॉक करें। चरण-दर-चरण उदाहरणों के साथ दृश्यात्मक रूप से आकर्षक दस्तावेज़ बनाना सीखें।
type: docs
weight: 14
url: /hi/java/document-conversion-and-export/using-document-shapes/
---

## जावा के लिए Aspose.Words में दस्तावेज़ आकृतियों का उपयोग करने का परिचय

इस व्यापक गाइड में, हम जावा के लिए Aspose.Words में दस्तावेज़ आकृतियों की दुनिया में गहराई से उतरेंगे। जब दृष्टिगत रूप से आकर्षक और इंटरैक्टिव दस्तावेज़ बनाने की बात आती है तो आकार आवश्यक तत्व होते हैं। चाहे आपको कॉलआउट, बटन, चित्र या वॉटरमार्क जोड़ने की आवश्यकता हो, जावा के लिए Aspose.Words इसे कुशलतापूर्वक करने के लिए उपकरण प्रदान करता है। आइए जानें कि स्रोत कोड उदाहरणों के साथ चरण दर चरण इन आकृतियों का उपयोग कैसे करें।

## दस्तावेज़ आकृतियों के साथ आरंभ करना

 इससे पहले कि हम कोड में कूदें, आइए अपना परिवेश स्थापित करें। सुनिश्चित करें कि आपके प्रोजेक्ट में जावा के लिए Aspose.Words एकीकृत है। यदि आपने पहले से नहीं किया है, तो आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं[जावा के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/)

## दस्तावेज़ों में आकृतियाँ जोड़ना

### ग्रुपशेप सम्मिलित करना

 ए`GroupShape` आपको अनेक आकृतियों को एक साथ समूहित करने की अनुमति देता है। यहां बताया गया है कि आप कैसे बना सकते हैं और सम्मिलित कर सकते हैं`GroupShape`:

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### टेक्स्ट बॉक्स आकार सम्मिलित करना

 टेक्स्ट बॉक्स आकार सम्मिलित करने के लिए, आप इसका उपयोग कर सकते हैं`insertShape` विधि जैसा कि नीचे दिए गए उदाहरण में दिखाया गया है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## आकार गुणों में हेरफेर

### पहलू अनुपात का प्रबंधन

आप यह नियंत्रित कर सकते हैं कि किसी आकृति का पक्षानुपात लॉक है या नहीं। यहां किसी आकृति के पहलू अनुपात को अनलॉक करने का तरीका बताया गया है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### टेबल सेल में एक आकृति रखना

यदि आपको तालिका सेल के अंदर कोई आकृति रखने की आवश्यकता है, तो आप इसे निम्नलिखित कोड से प्राप्त कर सकते हैं:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); // तालिका सेल के बाहर आकृति प्रदर्शित करें यदि इसे किसी सेल में रखा जाएगा।
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## स्मार्टआर्ट आकृतियों के साथ कार्य करना

### स्मार्टआर्ट आकृतियों का पता लगाना

आप निम्नलिखित कोड का उपयोग करके किसी दस्तावेज़ में स्मार्टआर्ट आकृतियों का पता लगा सकते हैं:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### स्मार्टआर्ट ड्रॉइंग अपडेट कर रहा है

किसी दस्तावेज़ में स्मार्टआर्ट ड्रॉइंग को अपडेट करने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## निष्कर्ष

इस गाइड में, हमने जावा के लिए Aspose.Words में दस्तावेज़ आकृतियों की दुनिया का पता लगाया है। आपने सीखा है कि अपने दस्तावेज़ों में विभिन्न आकृतियाँ कैसे जोड़ें, उनके गुणों में हेरफेर करें और स्मार्टआर्ट आकृतियों के साथ काम करें। इस ज्ञान के साथ, आप आसानी से दिखने में आकर्षक और इंटरैक्टिव दस्तावेज़ बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### जावा के लिए Aspose.Words क्या है?

Aspose.Words for Java एक जावा लाइब्रेरी है जो डेवलपर्स को Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और परिवर्तित करने की अनुमति देती है। यह विभिन्न प्रारूपों में दस्तावेज़ों के साथ काम करने के लिए सुविधाओं और उपकरणों की एक विस्तृत श्रृंखला प्रदान करता है।

### मैं जावा के लिए Aspose.Words कैसे डाउनलोड कर सकता हूं?

 आप इस लिंक का अनुसरण करके Aspose वेबसाइट से Java के लिए Aspose.Words डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Words डाउनलोड करें](https://releases.aspose.com/words/java/)

### दस्तावेज़ आकृतियों का उपयोग करने के क्या लाभ हैं?

दस्तावेज़ आकार आपके दस्तावेज़ों में दृश्य तत्व और अन्तरक्रियाशीलता जोड़ते हैं, जिससे वे अधिक आकर्षक और जानकारीपूर्ण बन जाते हैं। आकृतियों के साथ, आप समग्र उपयोगकर्ता अनुभव को बढ़ाते हुए कॉलआउट, बटन, चित्र, वॉटरमार्क और बहुत कुछ बना सकते हैं।

### क्या मैं आकृतियों का स्वरूप अनुकूलित कर सकता हूँ?

हां, आप आकार, स्थिति, घुमाव और रंग भरने जैसे गुणों को समायोजित करके आकृतियों के स्वरूप को अनुकूलित कर सकते हैं। जावा के लिए Aspose.Words आकार अनुकूलन के लिए व्यापक विकल्प प्रदान करता है।

### क्या जावा के लिए Aspose.Words स्मार्टआर्ट के साथ संगत है?

हां, जावा के लिए Aspose.Words स्मार्टआर्ट आकृतियों का समर्थन करता है, जिससे आप अपने दस्तावेज़ों में जटिल आरेखों और ग्राफिक्स के साथ काम कर सकते हैं।