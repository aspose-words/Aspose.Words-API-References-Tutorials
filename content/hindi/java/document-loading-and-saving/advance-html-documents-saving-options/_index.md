---
title: Aspose.Words Java के साथ उन्नत HTML दस्तावेज़ बचत विकल्प
linktitle: HTML दस्तावेज़ों को इसके साथ सहेजना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Words के साथ विभिन्न उन्नत HTML दस्तावेज़ बचत विकल्पों को शामिल किया है। ये विकल्प आपको उच्च-गुणवत्ता वाला HTML बनाने में सशक्त बनाते हैं।
type: docs
weight: 16
url: /hi/java/document-loading-and-saving/advance-html-documents-saving-options/
---

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Words द्वारा प्रदान किए गए उन्नत HTML दस्तावेज़ बचत विकल्पों का पता लगाएंगे। Aspose.Words Word दस्तावेज़ों के साथ काम करने के लिए एक शक्तिशाली जावा एपीआई है, और यह दस्तावेज़ हेरफेर और रूपांतरण के लिए कई प्रकार की सुविधाएँ प्रदान करता है।

## 1 परिचय
जावा के लिए Aspose.Words आपको प्रोग्रामेटिक रूप से Word दस्तावेज़ों के साथ काम करने की अनुमति देता है। इस ट्यूटोरियल में, हम उन्नत HTML दस्तावेज़ बचत विकल्पों पर ध्यान केंद्रित करेंगे, जो आपको यह नियंत्रित करने में सक्षम बनाता है कि Word दस्तावेज़ों को HTML में कैसे परिवर्तित किया जाता है।

## 2. राउंडट्रिप जानकारी निर्यात करें
`exportRoundtripInformation` विधि आपको राउंडट्रिप जानकारी को संरक्षित करते हुए Word दस्तावेज़ों को HTML में निर्यात करने की अनुमति देती है। यह जानकारी तब उपयोगी हो सकती है जब आप किसी दस्तावेज़-विशिष्ट विवरण को खोए बिना HTML को वापस वर्ड प्रारूप में परिवर्तित करना चाहते हैं।

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. फ़ॉन्ट्स को Base64 के रूप में निर्यात करें
 साथ`exportFontsAsBase64` विधि, आप दस्तावेज़ में उपयोग किए गए फ़ॉन्ट को HTML में बेस64-एन्कोडेड डेटा के रूप में निर्यात कर सकते हैं। यह सुनिश्चित करता है कि HTML प्रतिनिधित्व मूल Word दस्तावेज़ के समान फ़ॉन्ट शैलियों को बरकरार रखता है।

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. निर्यात संसाधन
`exportResources` विधि आपको सीएसएस स्टाइलशीट के प्रकार को निर्दिष्ट करने और फ़ॉन्ट संसाधनों को निर्यात करने की अनुमति देती है। आप HTML में संसाधनों के लिए एक संसाधन फ़ोल्डर और एक उपनाम भी सेट कर सकते हैं।

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. मेटाफ़ाइल्स को EMF या WMF में कनवर्ट करें
`convertMetafilesToEmfOrWmf`विधि आपको दस्तावेज़ में मेटाफ़ाइलों को EMF या WMF प्रारूप में परिवर्तित करने की अनुमति देती है, जिससे HTML में अनुकूलता और सुचारू प्रतिपादन सुनिश्चित होता है।

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया।
}
```

## 6. मेटाफ़ाइल्स को एसवीजी में कनवर्ट करें
 उपयोग`convertMetafilesToSvg` मेटाफ़ाइल्स को एसवीजी प्रारूप में परिवर्तित करने की विधि। यह प्रारूप HTML दस्तावेज़ों में वेक्टर ग्राफ़िक्स प्रदर्शित करने के लिए आदर्श है।

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया।
}
```

## 7. सीएसएस क्लास नाम उपसर्ग जोड़ें
 साथ`addCssClassNamePrefix` विधि, आप निर्यातित HTML में CSS वर्ग नामों में एक उपसर्ग जोड़ सकते हैं। यह मौजूदा शैलियों के साथ टकराव को रोकने में मदद करता है।

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. एमएचटीएमएल संसाधनों के लिए सीआईडी यूआरएल निर्यात करें
`exportCidUrlsForMhtmlResources` दस्तावेज़ों को एमएचटीएमएल प्रारूप में सहेजते समय विधि का उपयोग किया जाता है। यह संसाधनों के लिए कंटेंट-आईडी यूआरएल निर्यात करने की अनुमति देता है।

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया।
}
```

## 9. फ़ॉन्ट नाम हल करें
`resolveFontNames` विधि HTML प्रारूप में दस्तावेज़ों को सहेजते समय फ़ॉन्ट नामों को हल करने में मदद करती है, जिससे विभिन्न प्लेटफार्मों पर लगातार प्रतिपादन सुनिश्चित होता है।

```java
@Test
public void resolveFontNames() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया।
}
```

## 10. टेक्स्ट इनपुट फॉर्म फ़ील्ड को टेक्स्ट के रूप में निर्यात करें
`exportTextInputFormFieldAsText` विधि HTML में फ़ील्ड को सादे पाठ के रूप में निर्यात करती है, जिससे वे आसानी से पढ़ने योग्य और संपादन योग्य हो जाते हैं।

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया।
}
```

## 11. निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Words द्वारा प्रदान किए गए उन्नत HTML दस्तावेज़ बचत विकल्पों का पता लगाया। ये विकल्प आपको रूपांतरण प्रक्रिया पर बेहतर नियंत्रण प्रदान करते हैं, जिससे आप ऐसे HTML दस्तावेज़ बना सकते हैं जो मूल Word दस्तावेज़ों से काफी मिलते-जुलते हैं।

## 12.अक्सर पूछे जाने वाले प्रश्न
जावा और HTML दस्तावेज़ बचत विकल्पों के लिए Aspose.Words के साथ काम करने के बारे में अक्सर पूछे जाने वाले कुछ प्रश्न यहां दिए गए हैं:

### Q1: मैं जावा के लिए Aspose.Words का उपयोग करके HTML को वापस वर्ड फॉर्मेट में कैसे परिवर्तित कर सकता हूं?
 HTML को वापस वर्ड फॉर्मेट में बदलने के लिए, आप Aspose.Words API का उपयोग कर सकते हैं`load` HTML दस्तावेज़ को लोड करने और फिर उसे Word प्रारूप में सहेजने की विधि।

### Q2: क्या मैं HTML में निर्यात करते समय CSS शैलियों को अनुकूलित कर सकता हूँ?
 हाँ, आप HTML में प्रयुक्त स्टाइलशीट को संशोधित करके या इसका उपयोग करके CSS शैलियों को अनुकूलित कर सकते हैं`addCssClassNamePrefix` सीएसएस वर्ग नामों में उपसर्ग जोड़ने की विधि।

### Q3: क्या वेब डिस्प्ले के लिए HTML आउटपुट को अनुकूलित करने का कोई तरीका है?
हां, आप फ़ॉन्ट को बेस64 के रूप में निर्यात करने और मेटाफ़ाइल को एसवीजी में परिवर्तित करने जैसे विकल्पों को कॉन्फ़िगर करके वेब डिस्प्ले के लिए HTML आउटपुट को अनुकूलित कर सकते हैं।

### Q4: क्या जटिल Word दस्तावेज़ों को HTML में परिवर्तित करते समय कोई सीमाएँ हैं?
जबकि Java के लिए Aspose.Words शक्तिशाली रूपांतरण क्षमताएं प्रदान करता है, जटिल लेआउट वाले जटिल Word दस्तावेज़ों को वांछित HTML आउटपुट प्राप्त करने के लिए अतिरिक्त पोस्ट-प्रोसेसिंग की आवश्यकता हो सकती है।
