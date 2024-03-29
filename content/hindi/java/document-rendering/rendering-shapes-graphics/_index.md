---
title: दस्तावेज़ों में आकृतियाँ और ग्राफ़िक्स प्रस्तुत करना
linktitle: दस्तावेज़ों में आकृतियाँ और ग्राफ़िक्स प्रस्तुत करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि जावा के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ों को आकृतियों और ग्राफ़िक्स के साथ कैसे बढ़ाया जाए। सहजता से दृश्यात्मक रूप से आश्चर्यजनक सामग्री बनाएं।
type: docs
weight: 12
url: /hi/java/document-rendering/rendering-shapes-graphics/
---

## परिचय

इस डिजिटल युग में, दस्तावेज़ों को अक्सर सादे पाठ से कहीं अधिक की आवश्यकता होती है। आकृतियाँ और ग्राफ़िक्स जोड़ने से जानकारी अधिक प्रभावी ढंग से संप्रेषित हो सकती है और आपके दस्तावेज़ देखने में आकर्षक बन सकते हैं। जावा के लिए Aspose.Words एक शक्तिशाली जावा एपीआई है जो आपको आकृतियों और ग्राफिक्स को जोड़ने और अनुकूलित करने सहित Word दस्तावेज़ों में हेरफेर करने की अनुमति देता है।

## जावा के लिए Aspose.Words के साथ शुरुआत करना

इससे पहले कि हम आकृतियाँ और ग्राफ़िक्स जोड़ें, आइए जावा के लिए Aspose.Words से शुरुआत करें। आपको अपना विकास परिवेश स्थापित करना होगा और Aspose.Words लाइब्रेरी को शामिल करना होगा। आरंभ करने के चरण यहां दिए गए हैं:

```java
// अपने मावेन प्रोजेक्ट में Aspose.Words जोड़ें
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-words</artifactId>
    <version>latest-version</version>
</dependency>

// Aspose.Words को आरंभ करें
Document doc = new Document();
```

## दस्तावेज़ों में आकृतियाँ जोड़ना

आकृतियाँ सरल आयतों से लेकर जटिल आरेखों तक हो सकती हैं। जावा के लिए Aspose.Words रेखाएं, आयत और वृत्त सहित विभिन्न प्रकार के आकार प्रदान करता है। अपने दस्तावेज़ में कोई आकृति जोड़ने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
// एक नया आकार बनाएं
Shape shape = new Shape(doc, ShapeType.RECTANGLE);

// आकृति को अनुकूलित करें
shape.setWidth(100);
shape.setHeight(50);
shape.setStrokeColor(Color.RED);
shape.setFillColor(Color.YELLOW);

// दस्तावेज़ में आकृति सम्मिलित करें
doc.getFirstSection().getBody().getFirstParagraph().appendChild(shape);
```

## छवियाँ सम्मिलित करना

छवियाँ आपके दस्तावेज़ों को महत्वपूर्ण रूप से बढ़ा सकती हैं। जावा के लिए Aspose.Words आपको आसानी से छवियां सम्मिलित करने की अनुमति देता है:

```java
// एक छवि फ़ाइल लोड करें
byte[] imageBytes = Files.readAllBytes(Paths.get("path/to/your/image.png"));
Shape imageShape = new Shape(doc, ShapeType.IMAGE);
imageShape.getImageData().setImage(imageBytes);
doc.getFirstSection().getBody().getFirstParagraph().appendChild(imageShape);
```

## आकृतियों को अनुकूलित करना

आप आकृतियों के रंग, बॉर्डर और अन्य गुणों को बदलकर उन्हें और अधिक अनुकूलित कर सकते हैं। इसे कैसे करें इसका एक उदाहरण यहां दिया गया है:

```java
shape.setStrokeColor(Color.BLUE);
shape.setFillColor(Color.GREEN);
shape.getStroke().setWeight(2.0);
shape.setShadowEnabled(true);
```

## स्थिति निर्धारण और आकार निर्धारण

दस्तावेज़ के लेआउट के लिए आकृतियों की सटीक स्थिति और आकार महत्वपूर्ण हैं। जावा के लिए Aspose.Words इन गुणों को सेट करने के तरीके प्रदान करता है:

```java
shape.setLeft(100);
shape.setTop(200);
shape.setWidth(150);
shape.setHeight(75);
```

## आकृतियों के भीतर पाठ के साथ कार्य करना

आकृतियों में टेक्स्ट भी हो सकता है. आप जावा के लिए Aspose.Words का उपयोग करके आकृतियों के भीतर टेक्स्ट जोड़ और प्रारूपित कर सकते हैं:

```java
shape.getTextPath().setText("This is some text within the shape");
shape.getTextPath().setFontFamily("Arial");
shape.getTextPath().setFontSize(12);
```

## आकृतियों का समूहन

अधिक जटिल आरेख या व्यवस्था बनाने के लिए, आप आकृतियों को एक साथ समूहित कर सकते हैं:

```java
ShapeCollection group = new ShapeCollection(doc);
group.add(shape1);
group.add(shape2);
doc.getFirstSection().getBody().getFirstParagraph().appendChild(group);
```

## आकृतियों का Z-क्रम

आप Z-क्रम का उपयोग करके आकृतियों के प्रदर्शित होने के क्रम को नियंत्रित कर सकते हैं:

```java
shape1.setZOrder(1); // सामने लाना
shape2.setZOrder(0); // वापस भेजो
```

## दस्तावेज़ सहेजा जा रहा है

एक बार जब आप अपनी आकृतियाँ और ग्राफ़िक्स जोड़ और अनुकूलित कर लें, तो दस्तावेज़ सहेजें:

```java
doc.save("output.docx");
```

## सामान्य उपयोग के मामले

जावा के लिए Aspose.Words बहुमुखी है और इसका उपयोग विभिन्न परिदृश्यों में किया जा सकता है:

- चार्ट और रेखाचित्रों के साथ रिपोर्ट तैयार करना।
- आकर्षक ग्राफिक्स वाले ब्रोशर बनाना।
- डिजाइनिंग प्रमाण पत्र और पुरस्कार.
- दस्तावेज़ों में एनोटेशन और कॉलआउट जोड़ना।

## समस्या निवारण युक्तियों

यदि आप आकृतियों और ग्राफिक्स के साथ काम करते समय समस्याओं का सामना करते हैं, तो समाधान के लिए जावा दस्तावेज़ीकरण या सामुदायिक मंचों के लिए Aspose.Words देखें। सामान्य समस्याओं में छवि प्रारूप अनुकूलता और फ़ॉन्ट-संबंधित समस्याएं शामिल हैं।

## निष्कर्ष

अपने दस्तावेज़ों को आकृतियों और ग्राफ़िक्स के साथ बढ़ाने से उनकी दृश्य अपील और जानकारी संप्रेषित करने की प्रभावशीलता में काफी सुधार हो सकता है। जावा के लिए Aspose.Words इस कार्य को निर्बाध रूप से पूरा करने के लिए उपकरणों का एक मजबूत सेट प्रदान करता है। आज ही दृश्यमान आश्चर्यजनक दस्तावेज़ बनाना शुरू करें!

## अक्सर पूछे जाने वाले प्रश्न

### मैं अपने दस्तावेज़ में किसी आकृति का आकार कैसे बदल सकता हूँ?

 किसी आकृति का आकार बदलने के लिए, इसका उपयोग करें`setWidth` और`setHeight` आकृति वस्तु पर विधियाँ। उदाहरण के लिए, 150 पिक्सेल चौड़ी और 75 पिक्सेल लम्बी आकृति बनाने के लिए:

```java
shape.setWidth(150);
shape.setHeight(75);
```

### क्या मैं किसी दस्तावेज़ में अनेक आकृतियाँ जोड़ सकता हूँ?

हाँ, आप किसी दस्तावेज़ में अनेक आकृतियाँ जोड़ सकते हैं। बस कई आकार की वस्तुएं बनाएं और उन्हें दस्तावेज़ के मुख्य भाग या एक विशिष्ट पैराग्राफ में जोड़ें।

### मैं किसी आकृति का रंग कैसे बदलूं?

आप स्ट्रोक रंग सेट करके और आकृति वस्तु के रंग गुणों को भरकर किसी आकृति का रंग बदल सकते हैं। उदाहरण के लिए, स्ट्रोक रंग को नीला और भरण रंग को हरा पर सेट करने के लिए:

```java
shape.setStrokeColor(Color.BLUE);
shape.setFillColor(Color.GREEN);
```

### क्या मैं किसी आकृति के अंदर टेक्स्ट जोड़ सकता हूँ?

 हाँ, आप किसी आकृति के अंदर टेक्स्ट जोड़ सकते हैं। उपयोग`getTextPath` पाठ को सेट करने और उसके स्वरूपण को अनुकूलित करने के लिए आकृति की संपत्ति।

### मैं आकृतियों को एक विशिष्ट क्रम में कैसे व्यवस्थित कर सकता हूँ?

 आप Z-ऑर्डर प्रॉपर्टी का उपयोग करके आकृतियों के क्रम को नियंत्रित कर सकते हैं। ठीक`ZOrder` आकृतियों के ढेर में उसकी स्थिति निर्धारित करने के लिए किसी आकृति का गुण। कम मूल्यों को पीछे भेजा जाता है, जबकि उच्च मूल्यों को सामने लाया जाता है।