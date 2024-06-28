---
title: जावा के लिए Aspose.Words में दस्तावेज़ों को जोड़ना और जोड़ना
linktitle: दस्तावेज़ों को जोड़ना और जोड़ना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके आसानी से दस्तावेज़ों को जोड़ना और जोड़ना सीखें। फ़ॉर्मेटिंग सुरक्षित रखें, हेडर फ़ुटर प्रबंधित करें, और बहुत कुछ।
type: docs
weight: 30
url: /hi/java/document-manipulation/joining-and-appending-documents/
---

## जावा के लिए Aspose.Words में दस्तावेज़ों को जोड़ने और जोड़ने का परिचय

इस ट्यूटोरियल में, हम देखेंगे कि जावा लाइब्रेरी के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को कैसे जोड़ा और जोड़ा जाए। आप सीखेंगे कि फ़ॉर्मेटिंग और संरचना को संरक्षित करते हुए एकाधिक दस्तावेज़ों को निर्बाध रूप से कैसे मर्ज किया जाए।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Words for Java API सेटअप है।

## दस्तावेज़ में शामिल होने के विकल्प

### सरल परिशिष्ट

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### आयात प्रारूप विकल्पों के साथ जोड़ें

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### रिक्त दस्तावेज़ में जोड़ें

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### पृष्ठ संख्या रूपांतरण के साथ जोड़ें

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // NUMPAGES फ़ील्ड कनवर्ट करें
dstDoc.updatePageLayout(); // सही नंबरिंग के लिए पेज लेआउट अपडेट करें
```

## विभिन्न पेज सेटअप को संभालना

विभिन्न पेज सेटअप के साथ दस्तावेज़ जोड़ते समय:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// सुनिश्चित करें कि पेज सेटअप सेटिंग्स गंतव्य दस्तावेज़ से मेल खाती हैं
```

## विभिन्न शैलियों के साथ दस्तावेज़ों को जोड़ना

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## स्मार्ट स्टाइल व्यवहार

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## DocumentBuilder के साथ दस्तावेज़ सम्मिलित करना

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## स्रोत क्रमांकन रखना

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## टेक्स्ट बॉक्स संभालना

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## शीर्षलेख और पाद लेख प्रबंधित करना

### शीर्षलेख और पादलेख लिंक करना

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### शीर्षलेख और पाद लेख को अनलिंक करना

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## निष्कर्ष

जावा के लिए Aspose.Words दस्तावेज़ों को जोड़ने और जोड़ने के लिए लचीले और शक्तिशाली उपकरण प्रदान करता है, चाहे आपको फ़ॉर्मेटिंग बनाए रखने, विभिन्न पेज सेटअप को संभालने, या हेडर और फ़ुटर प्रबंधित करने की आवश्यकता हो। अपनी विशिष्ट दस्तावेज़ प्रसंस्करण आवश्यकताओं को पूरा करने के लिए इन तकनीकों का प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं विभिन्न शैलियों वाले दस्तावेज़ों को निर्बाध रूप से कैसे जोड़ सकता हूँ?

 विभिन्न शैलियों वाले दस्तावेज़ों को जोड़ने के लिए, उपयोग करें`ImportFormatMode.USE_DESTINATION_STYLES` जोड़ते समय.

### क्या मैं दस्तावेज़ जोड़ते समय पृष्ठ क्रमांकन सुरक्षित रख सकता हूँ?

 हाँ, आप इसका उपयोग करके पृष्ठ क्रमांकन को सुरक्षित रख सकते हैं`convertNumPageFieldsToPageRef` विधि और पेज लेआउट को अद्यतन करना।

### स्मार्ट स्टाइल बिहेवियर क्या है?

 स्मार्ट स्टाइल व्यवहार दस्तावेज़ जोड़ते समय सुसंगत शैलियों को बनाए रखने में मदद करता है। इसके साथ प्रयोग करें`ImportFormatOptions` बेहतर परिणाम के लिए.

### दस्तावेज़ जोड़ते समय मैं टेक्स्ट बॉक्स कैसे संभाल सकता हूँ?

तय करना`importFormatOptions.setIgnoreTextBoxes(false)` जोड़ने के दौरान टेक्स्ट बॉक्स शामिल करना।

### यदि मैं दस्तावेज़ों के बीच हेडर और फ़ुटर को लिंक/अनलिंक करना चाहूँ तो क्या होगा?

 आप हेडर और फ़ुटर को इससे लिंक कर सकते हैं`linkToPrevious(true)` या उन्हें अनलिंक करें`linkToPrevious(false)` जरुरत के अनुसार।