---
title: दस्तावेज़ वॉटरमार्किंग और पेज सेटअप
linktitle: दस्तावेज़ वॉटरमार्किंग और पेज सेटअप
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि वॉटरमार्क कैसे लागू करें और जावा के लिए Aspose.Words के साथ पेज कॉन्फ़िगरेशन कैसे सेट करें। स्रोत कोड के साथ एक व्यापक मार्गदर्शिका।
type: docs
weight: 13
url: /hi/java/document-styling/document-watermarking-page-setup/
---
## परिचय

दस्तावेज़ हेरफेर के क्षेत्र में, जावा के लिए Aspose.Words एक शक्तिशाली उपकरण के रूप में खड़ा है, जो डेवलपर्स को दस्तावेज़ प्रसंस्करण के हर पहलू पर नियंत्रण रखने की अनुमति देता है। इस व्यापक गाइड में, हम जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ वॉटरमार्किंग और पेज सेटअप की जटिलताओं को समझेंगे। चाहे आप एक अनुभवी डेवलपर हों या जावा दस्तावेज़ प्रसंस्करण की दुनिया में कदम रख रहे हों, यह चरण-दर-चरण मार्गदर्शिका आपको आवश्यक ज्ञान और स्रोत कोड से लैस करेगी।

## दस्तावेज़ वॉटरमार्किंग

### वॉटरमार्क जोड़ना

दस्तावेज़ों में वॉटरमार्क जोड़ना आपकी सामग्री की ब्रांडिंग या सुरक्षा के लिए महत्वपूर्ण हो सकता है। जावा के लिए Aspose.Words इस कार्य को सरल बनाता है। ऐसे:

```java
// दस्तावेज़ लोड करें
Document doc = new Document("document.docx");

// वॉटरमार्क बनाएं
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// वॉटरमार्क लगाएं
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// वॉटरमार्क डालें
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// दस्तावेज़ सहेजें
doc.save("document_with_watermark.docx");
```

### वॉटरमार्क अनुकूलित करना

आप फ़ॉन्ट, आकार, रंग और रोटेशन को समायोजित करके वॉटरमार्क को और अधिक अनुकूलित कर सकते हैं। यह लचीलापन सुनिश्चित करता है कि आपका वॉटरमार्क आपके दस्तावेज़ की शैली से सहजता से मेल खाता हो।

## पृष्ठ सेटअप

### पृष्ठ का आकार और अभिमुखीकरण

दस्तावेज़ स्वरूपण में पेज सेटअप महत्वपूर्ण है। जावा के लिए Aspose.Words पेज आकार और ओरिएंटेशन पर पूर्ण नियंत्रण प्रदान करता है:

```java
// दस्तावेज़ लोड करें
Document doc = new Document("document.docx");

// पेज का आकार A4 पर सेट करें
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// पेज ओरिएंटेशन को लैंडस्केप में बदलें
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// संशोधित दस्तावेज़ सहेजें
doc.save("formatted_document.docx");
```

### मार्जिन और पेज नंबरिंग

पेशेवर दस्तावेजों के लिए मार्जिन और पेज नंबरिंग पर सटीक नियंत्रण आवश्यक है। जावा के लिए Aspose.Words के साथ इसे हासिल करें:

```java
// दस्तावेज़ लोड करें
Document doc = new Document("document.docx");

// मार्जिन सेट करें
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// पृष्ठ क्रमांकन सक्षम करें
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// स्वरूपित दस्तावेज़ को सहेजें
doc.save("formatted_document.docx");
```

## पूछे जाने वाले प्रश्न

### मैं किसी दस्तावेज़ से वॉटरमार्क कैसे हटा सकता हूँ?

किसी दस्तावेज़ से वॉटरमार्क हटाने के लिए, आप दस्तावेज़ के आकारों को दोहरा सकते हैं और वॉटरमार्क का प्रतिनिधित्व करने वाले आकारों को हटा सकते हैं। यहाँ एक अंश है:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### क्या मैं एक ही दस्तावेज़ में एकाधिक वॉटरमार्क जोड़ सकता हूँ?

हाँ, आप अतिरिक्त शेप ऑब्जेक्ट बनाकर और उन्हें आवश्यकतानुसार स्थान देकर किसी दस्तावेज़ में एकाधिक वॉटरमार्क जोड़ सकते हैं।

### मैं लैंडस्केप ओरिएंटेशन में पेज का आकार कानूनी में कैसे बदलूं?

लैंडस्केप ओरिएंटेशन में पृष्ठ आकार को कानूनी पर सेट करने के लिए, पृष्ठ की चौड़ाई और ऊंचाई को निम्नानुसार संशोधित करें:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### वॉटरमार्क के लिए डिफ़ॉल्ट फ़ॉन्ट क्या है?

वॉटरमार्क के लिए डिफ़ॉल्ट फ़ॉन्ट Calibri है जिसका फ़ॉन्ट आकार 36 है।

### मैं किसी विशिष्ट पृष्ठ से आरंभ करके पृष्ठ संख्याएँ कैसे जोड़ सकता हूँ?

आप अपने दस्तावेज़ में प्रारंभिक पृष्ठ संख्या निम्नानुसार सेट करके इसे प्राप्त कर सकते हैं:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### मैं शीर्ष लेख या पाद लेख में टेक्स्ट को केंद्र-संरेखित कैसे करूँ?

आप शीर्ष लेख या पाद लेख के भीतर पैराग्राफ ऑब्जेक्ट पर सेटएलाइनमेंट विधि का उपयोग करके शीर्ष लेख या पाद लेख में पाठ को केंद्र-संरेखित कर सकते हैं।

## निष्कर्ष

इस व्यापक गाइड में, हमने जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ वॉटरमार्किंग और पेज सेटअप की कला का पता लगाया है। प्रदान किए गए स्रोत कोड स्निपेट और अंतर्दृष्टि से लैस, अब आपके पास अपने दस्तावेज़ों को चालाकी से हेरफेर करने और प्रारूपित करने के लिए उपकरण हैं। जावा के लिए Aspose.Words आपको आपके सटीक विनिर्देशों के अनुरूप पेशेवर, ब्रांडेड दस्तावेज़ बनाने का अधिकार देता है।

दस्तावेज़ हेरफेर में महारत हासिल करना डेवलपर्स के लिए एक मूल्यवान कौशल है, और जावा के लिए Aspose.Words इस यात्रा में आपका विश्वसनीय साथी है। आज ही शानदार दस्तावेज़ बनाना शुरू करें!