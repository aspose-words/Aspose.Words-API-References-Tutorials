---
title: Java के लिए Aspose.Words में दस्तावेज़ों को PDF के रूप में सहेजना
linktitle: दस्तावेज़ों को पीडीएफ के रूप में सहेजना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को PDF के रूप में सहेजना सीखें। फ़ॉन्ट, गुण और छवि गुणवत्ता अनुकूलित करें। पीडीएफ रूपांतरण के लिए एक व्यापक मार्गदर्शिका।
type: docs
weight: 22
url: /hi/java/document-loading-and-saving/saving-documents-as-pdf/
---

## जावा के लिए Aspose.Words में दस्तावेज़ों को पीडीएफ के रूप में सहेजने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि Java के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को PDF के रूप में कैसे सहेजा जाए। हम पीडीएफ रूपांतरण के विभिन्न पहलुओं को कवर करेंगे और प्रक्रिया को आसान बनाने के लिए कोड उदाहरण प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Words। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## किसी दस्तावेज़ को पीडीएफ में परिवर्तित करना

किसी Word दस्तावेज़ को PDF में बदलने के लिए, आप निम्नलिखित कोड स्निपेट का उपयोग कर सकते हैं:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 प्रतिस्थापित करें`"input.docx"` आपके Word दस्तावेज़ के पथ के साथ और`"output.pdf"` वांछित आउटपुट पीडीएफ फ़ाइल पथ के साथ।

## पीडीएफ सेव विकल्पों को नियंत्रित करना

 आप इसका उपयोग करके विभिन्न पीडीएफ सेव विकल्पों को नियंत्रित कर सकते हैं`PdfSaveOptions` कक्षा। उदाहरण के लिए, आप पीडीएफ दस्तावेज़ के लिए प्रदर्शन शीर्षक इस प्रकार सेट कर सकते हैं:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## पीडीएफ में फ़ॉन्ट एम्बेड करना

उत्पन्न पीडीएफ में फ़ॉन्ट एम्बेड करने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## दस्तावेज़ गुणों को अनुकूलित करना

आप जनरेट की गई पीडीएफ में दस्तावेज़ गुणों को अनुकूलित कर सकते हैं। उदाहरण के लिए:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## दस्तावेज़ संरचना निर्यात करना

 दस्तावेज़ संरचना को निर्यात करने के लिए, सेट करें`exportDocumentStructure` का विकल्प`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## छवि संपीड़न

आप निम्न कोड का उपयोग करके छवि संपीड़न को नियंत्रित कर सकते हैं:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## अंतिम मुद्रित संपत्ति को अद्यतन करना

पीडीएफ में "अंतिम मुद्रित" संपत्ति को अद्यतन करने के लिए, इसका उपयोग करें:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## डीएमएल 3डी प्रभावों का प्रतिपादन

डीएमएल 3डी प्रभावों के उन्नत प्रतिपादन के लिए, प्रतिपादन मोड सेट करें:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## छवियाँ प्रक्षेपित करना

आप छवि गुणवत्ता में सुधार के लिए छवि प्रक्षेप सक्षम कर सकते हैं:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## निष्कर्ष

जावा के लिए Aspose.Words लचीलेपन और अनुकूलन विकल्पों के साथ Word दस्तावेज़ों को पीडीएफ प्रारूप में परिवर्तित करने के लिए व्यापक क्षमताएं प्रदान करता है। आप पीडीएफ आउटपुट के विभिन्न पहलुओं को नियंत्रित कर सकते हैं, जिसमें फ़ॉन्ट, दस्तावेज़ गुण, छवि संपीड़न और बहुत कुछ शामिल हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ को PDF में कैसे परिवर्तित करूं?

किसी Word दस्तावेज़ को PDF में बदलने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 प्रतिस्थापित करें`"input.docx"` आपके Word दस्तावेज़ के पथ के साथ और`"output.pdf"` वांछित आउटपुट पीडीएफ फ़ाइल पथ के साथ।

### क्या मैं जावा के लिए Aspose.Words द्वारा उत्पन्न पीडीएफ में फ़ॉन्ट एम्बेड कर सकता हूं?

 हां, आप सेटिंग करके पीडीएफ में फ़ॉन्ट एम्बेड कर सकते हैं`setEmbedFullFonts` का विकल्प`true` में`PdfSaveOptions`. यहाँ एक उदाहरण है:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### मैं जेनरेट की गई पीडीएफ में दस्तावेज़ गुणों को कैसे अनुकूलित कर सकता हूं?

 आप इसका उपयोग करके पीडीएफ में दस्तावेज़ गुणों को अनुकूलित कर सकते हैं`setCustomPropertiesExport` विकल्प में`PdfSaveOptions`. उदाहरण के लिए:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Java के लिए Aspose.Words में छवि संपीड़न का उद्देश्य क्या है?

 छवि संपीड़न आपको उत्पन्न पीडीएफ में छवियों की गुणवत्ता और आकार को नियंत्रित करने की अनुमति देता है। आप इसका उपयोग करके छवि संपीड़न मोड सेट कर सकते हैं`setImageCompression` में`PdfSaveOptions`.

### मैं पीडीएफ में "अंतिम मुद्रित" संपत्ति को कैसे अपडेट करूं?

 आप सेटिंग करके पीडीएफ में "अंतिम मुद्रित" संपत्ति को अपडेट कर सकते हैं`setUpdateLastPrintedProperty` को`true` में`PdfSaveOptions`. यह पीडीएफ मेटाडेटा में अंतिम मुद्रित तिथि दर्शाएगा।

### पीडीएफ में कनवर्ट करते समय मैं छवि गुणवत्ता कैसे सुधार सकता हूं?

 छवि गुणवत्ता में सुधार करने के लिए, सेटिंग द्वारा छवि इंटरपोलेशन सक्षम करें`setInterpolateImages` को`true` में`PdfSaveOptions`. इसके परिणामस्वरूप पीडीएफ में चिकनी और उच्च गुणवत्ता वाली छवियां प्राप्त होंगी।