---
title: जावा के लिए Aspose.Words में टेक्स्ट ढूँढना और बदलना
linktitle: टेक्स्ट ढूँढना और बदलना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि जावा के लिए Aspose.Words के साथ Word दस्तावेज़ों में टेक्स्ट को कैसे ढूंढें और बदलें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका। अपने जावा दस्तावेज़ हेरफेर कौशल को बढ़ाएं।
type: docs
weight: 15
url: /hi/java/document-manipulation/finding-and-replacing-text/
---

## जावा के लिए Aspose.Words में टेक्स्ट ढूंढने और बदलने का परिचय

Aspose.Words for Java एक शक्तिशाली जावा एपीआई है जो आपको Word दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। Word दस्तावेज़ों से निपटते समय सामान्य कार्यों में से एक टेक्स्ट ढूंढना और बदलना है। चाहे आपको टेम्प्लेट में प्लेसहोल्डर्स को अपडेट करने की आवश्यकता हो या अधिक जटिल टेक्स्ट हेरफेर करने की आवश्यकता हो, जावा के लिए Aspose.Words आपके लक्ष्यों को कुशलतापूर्वक प्राप्त करने में आपकी सहायता कर सकता है।

## आवश्यक शर्तें

इससे पहले कि हम टेक्स्ट ढूंढने और बदलने के विवरण में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा विकास पर्यावरण
- जावा लाइब्रेरी के लिए Aspose.Words
- काम करने के लिए एक नमूना Word दस्तावेज़

 आप Aspose.Words for Java लाइब्रेरी से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## सरल पाठ ढूँढना और बदलना

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक डॉक्यूमेंटबिल्डर बनाएं
DocumentBuilder builder = new DocumentBuilder(doc);

// टेक्स्ट ढूंढें और बदलें
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

 इस उदाहरण में, हम एक Word दस्तावेज़ लोड करते हैं, एक बनाते हैं`DocumentBuilder` , और उपयोग करें`replace` दस्तावेज़ के भीतर "पुराने-पाठ" को "नये-पाठ" से खोजने और बदलने की विधि।

## रेगुलर एक्सप्रेशन का उपयोग करना

रेगुलर एक्सप्रेशन टेक्स्ट खोज और प्रतिस्थापन के लिए शक्तिशाली पैटर्न मिलान क्षमताएं प्रदान करते हैं। जावा के लिए Aspose.Words अधिक उन्नत खोज और प्रतिस्थापन कार्यों के लिए नियमित अभिव्यक्तियों का समर्थन करता है।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक डॉक्यूमेंटबिल्डर बनाएं
DocumentBuilder builder = new DocumentBuilder(doc);

// टेक्स्ट ढूंढने और बदलने के लिए रेगुलर एक्सप्रेशन का उपयोग करें
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

इस उदाहरण में, हम दस्तावेज़ के भीतर टेक्स्ट को खोजने और बदलने के लिए रेगुलर एक्सप्रेशन पैटर्न का उपयोग करते हैं।

## फ़ील्ड के अंदर टेक्स्ट को अनदेखा करना

आप खोजने और बदलने की कार्रवाई करते समय फ़ील्ड के अंदर पाठ को अनदेखा करने के लिए Aspose.Words को कॉन्फ़िगर कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक FindReplaceOptions इंस्टेंस बनाएं और IgnoreFields को सत्य पर सेट करें
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace("text-to-replace", "new-text", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह तब उपयोगी होता है जब आप फ़ील्ड के अंदर के टेक्स्ट, जैसे मर्ज फ़ील्ड, को प्रतिस्थापित होने से रोकना चाहते हैं।

## अंदर पाठ को अनदेखा करना संशोधन हटाएँ

आप खोजने और बदलने के संचालन के दौरान डिलीट संशोधनों के अंदर पाठ को अनदेखा करने के लिए Aspose.Words को कॉन्फ़िगर कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक FindReplaceOptions इंस्टेंस बनाएं और IgnoreDeleted को सत्य पर सेट करें
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace("text-to-replace", "new-text", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको ट्रैक किए गए परिवर्तनों में हटाने के लिए चिह्नित किए गए टेक्स्ट को प्रतिस्थापित होने से बाहर करने की अनुमति देता है।

## सम्मिलित संशोधनों के अंदर पाठ को अनदेखा करना

आप खोजने और बदलने के संचालन के दौरान सम्मिलित संशोधनों के अंदर पाठ को अनदेखा करने के लिए Aspose.Words को कॉन्फ़िगर कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक FindReplaceOptions इंस्टेंस बनाएं और IgnoreInserted को सत्य पर सेट करें
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace("text-to-replace", "new-text", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको उस टेक्स्ट को प्रतिस्थापित होने से बाहर करने की अनुमति देता है जिसे ट्रैक किए गए परिवर्तनों में सम्मिलित के रूप में चिह्नित किया गया है।

## टेक्स्ट को HTML से बदलना

टेक्स्ट को HTML सामग्री से बदलने के लिए आप जावा के लिए Aspose.Words का उपयोग कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// कस्टम रिप्लेसिंग कॉलबैक के साथ FindReplaceOptions इंस्टेंस बनाएं
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace("text-to-replace", "new-html-content", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

 इस उदाहरण में, हम एक कस्टम का उपयोग करते हैं`ReplaceWithHtmlEvaluator` टेक्स्ट को HTML सामग्री से बदलने के लिए।

## हेडर और फ़ुटर में टेक्स्ट बदलना

आप अपने Word दस्तावेज़ के शीर्षलेख और पादलेख में टेक्स्ट ढूंढ और बदल सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// शीर्ष लेख और पाद लेख का संग्रह प्राप्त करें
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// वह हेडर या फ़ूटर प्रकार चुनें जिसमें आप टेक्स्ट को बदलना चाहते हैं (उदाहरण के लिए, हेडरफुटरटाइप.फ़ूटर_प्राइमरी)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// एक FindReplaceOptions इंस्टेंस बनाएं और इसे पाद लेख की सीमा पर लागू करें
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको विशेष रूप से हेडर और फ़ूटर में टेक्स्ट प्रतिस्थापन करने की अनुमति देता है।

## शीर्ष लेख और पाद लेख आदेशों के लिए परिवर्तन दिखाए जा रहे हैं

आप अपने दस्तावेज़ में हेडर और फ़ुटर ऑर्डर के लिए परिवर्तन दिखाने के लिए Aspose.Words का उपयोग कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// पहला खंड प्राप्त करें
Section firstPageSection = doc.getFirstSection();

// एक FindReplaceOptions इंस्टेंस बनाएं और इसे दस्तावेज़ की सीमा पर लागू करें
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//शीर्ष लेख और पाद लेख क्रम को प्रभावित करने वाले टेक्स्ट को बदलें
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको अपने दस्तावेज़ में हेडर और फ़ूटर ऑर्डर से संबंधित परिवर्तनों की कल्पना करने की अनुमति देता है।

## टेक्स्ट को फ़ील्ड्स से बदलना

आप जावा के लिए Aspose.Words का उपयोग करके टेक्स्ट को फ़ील्ड से बदल सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक FindReplaceOptions इंस्टेंस बनाएं और फ़ील्ड के लिए एक कस्टम रिप्लेसिंग कॉलबैक सेट करें
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

 इस उदाहरण में, हम टेक्स्ट को फ़ील्ड से प्रतिस्थापित करते हैं और फ़ील्ड प्रकार निर्दिष्ट करते हैं (उदाहरण के लिए,`FieldType.FIELD_MERGE_FIELD`).

## एक मूल्यांकनकर्ता के साथ प्रतिस्थापन

आप प्रतिस्थापन पाठ को गतिशील रूप से निर्धारित करने के लिए एक कस्टम मूल्यांकनकर्ता का उपयोग कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक FindReplaceOptions इंस्टेंस बनाएं और एक कस्टम रिप्लेसिंग कॉलबैक सेट करें
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

इस उदाहरण में, हम एक कस्टम मूल्यांकनकर्ता का उपयोग करते हैं (`MyReplaceEvaluator`) टेक्स्ट को बदलने के लिए।

## रेगेक्स के साथ प्रतिस्थापित करना

जावा के लिए Aspose.Words आपको रेगुलर एक्सप्रेशन का उपयोग करके टेक्स्ट को बदलने की अनुमति देता है।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// टेक्स्ट ढूंढने और बदलने के लिए रेगुलर एक्सप्रेशन का उपयोग करें
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

इस उदाहरण में, हम दस्तावेज़ के भीतर टेक्स्ट को खोजने और बदलने के लिए रेगुलर एक्सप्रेशन पैटर्न का उपयोग करते हैं।

## प्रतिस्थापन पैटर्न के भीतर पहचानना और प्रतिस्थापन

आप जावा के लिए Aspose.Words का उपयोग करके प्रतिस्थापन पैटर्न के भीतर पहचान और प्रतिस्थापन कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

//UseSubstitutions को सत्य पर सेट करके FindReplaceOptions इंस्टेंस बनाएं
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// टेक्स्ट को पैटर्न से प्रतिस्थापित करते समय विकल्पों का उपयोग करें
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको अधिक उन्नत प्रतिस्थापनों के लिए प्रतिस्थापन पैटर्न के भीतर प्रतिस्थापन करने की अनुमति देता है।

## एक स्ट्रिंग के साथ प्रतिस्थापित करना

आप जावा के लिए Aspose.Words का उपयोग करके टेक्स्ट को एक साधारण स्ट्रिंग से बदल सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// टेक्स्ट को एक स्ट्रिंग से बदलें
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

इस उदाहरण में, हम दस्तावेज़ के भीतर "टेक्स्ट-टू-रिप्लेस" को "न्यू-स्ट्रिंग" से बदल देते हैं।

## लीगेसी ऑर्डर का उपयोग करना

ढूंढने और बदलने की कार्रवाई करते समय आप लीगेसी ऑर्डर का उपयोग कर सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक FindReplaceOptions इंस्टेंस बनाएं और UseLegacyOrder को सत्य पर सेट करें
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// टेक्स्ट बदलते समय विकल्पों का उपयोग करें
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको कार्यों को खोजने और बदलने के लिए लीगेसी ऑर्डर का उपयोग करने की अनुमति देता है।

## किसी तालिका में टेक्स्ट बदलना

आप अपने Word दस्तावेज़ में तालिकाओं के भीतर टेक्स्ट ढूंढ और बदल सकते हैं।

```java
// दस्तावेज़ लोड करें
Document doc = new Document("your-document.docx");

// एक विशिष्ट तालिका प्राप्त करें (उदाहरण के लिए, पहली तालिका)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// तालिका में टेक्स्ट को बदलने के लिए FindReplaceOptions का उपयोग करें
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// संशोधित दस्तावेज़ सहेजें
doc.save("modified-document.docx");
```

यह आपको विशेष रूप से तालिकाओं के भीतर पाठ प्रतिस्थापन करने की अनुमति देता है।

## निष्कर्ष

जावा के लिए Aspose.Words Word दस्तावेज़ों में टेक्स्ट खोजने और बदलने के लिए व्यापक क्षमताएं प्रदान करता है। चाहे आपको नियमित अभिव्यक्ति, फ़ील्ड हेरफेर, या कस्टम मूल्यांकनकर्ताओं का उपयोग करके सरल पाठ प्रतिस्थापन या अधिक उन्नत संचालन करने की आवश्यकता हो, जावा के लिए Aspose.Words ने आपको कवर किया है। इस शक्तिशाली जावा लाइब्रेरी की पूरी क्षमता का उपयोग करने के लिए Aspose द्वारा प्रदान किए गए व्यापक दस्तावेज़ और उदाहरणों का पता लगाना सुनिश्चित करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Words कैसे डाउनलोड करूं?

 आप वेबसाइट पर जाकर Aspose.Words for Java डाउनलोड कर सकते हैं[इस लिंक](https://releases.aspose.com/words/java/).

### क्या मैं टेक्स्ट प्रतिस्थापन के लिए रेगुलर एक्सप्रेशन का उपयोग कर सकता हूँ?

हां, आप जावा के लिए Aspose.Words में टेक्स्ट प्रतिस्थापन के लिए नियमित अभिव्यक्तियों का उपयोग कर सकते हैं। यह आपको अधिक उन्नत और लचीले खोज और प्रतिस्थापन संचालन करने की अनुमति देता है।

### मैं प्रतिस्थापन के दौरान फ़ील्ड के अंदर के पाठ को कैसे अनदेखा कर सकता हूँ?

 प्रतिस्थापन के दौरान फ़ील्ड के अंदर पाठ को अनदेखा करने के लिए, आप सेट कर सकते हैं`IgnoreFields` की संपत्ति`FindReplaceOptions` को`true`यह सुनिश्चित करता है कि फ़ील्ड के भीतर का टेक्स्ट, जैसे मर्ज फ़ील्ड, को प्रतिस्थापन से बाहर रखा गया है।

### क्या मैं शीर्षलेख और पादलेख के अंदर पाठ को बदल सकता हूँ?

 हाँ, आप अपने Word दस्तावेज़ के शीर्षलेख और पादलेख के अंदर पाठ को बदल सकते हैं। बस उचित शीर्षलेख या पादलेख तक पहुंचें और इसका उपयोग करें`replace` वांछित के साथ विधि`FindReplaceOptions`.

### यूज़लिगेसीऑर्डर विकल्प किसके लिए है?

`UseLegacyOrder` विकल्प में`FindReplaceOptions` ढूंढने और बदलने की कार्रवाई करते समय आपको लीगेसी ऑर्डर का उपयोग करने की अनुमति देता है। यह उन कुछ परिदृश्यों में उपयोगी हो सकता है जहां विरासती क्रम व्यवहार वांछित है।