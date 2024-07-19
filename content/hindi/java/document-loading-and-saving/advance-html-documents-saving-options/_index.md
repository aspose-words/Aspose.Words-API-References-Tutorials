---
title: Aspose.Words Java के साथ उन्नत HTML दस्तावेज़ सहेजने के विकल्प
linktitle: HTML दस्तावेज़ों को सहेजना
second_title: Aspose.Words जावा दस्तावेज़ प्रसंस्करण एपीआई
description: इस ट्यूटोरियल में, हमने Aspose.Words for Java के साथ विभिन्न उन्नत HTML दस्तावेज़ सहेजने के विकल्पों को कवर किया है। ये विकल्प आपको उच्च-गुणवत्ता वाला HTML बनाने में सक्षम बनाते हैं
type: docs
weight: 16
url: /hi/java/document-loading-and-saving/advance-html-documents-saving-options/
---

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Words द्वारा प्रदान किए गए उन्नत HTML दस्तावेज़ सहेजने के विकल्पों का पता लगाएंगे। Aspose.Words Word दस्तावेज़ों के साथ काम करने के लिए एक शक्तिशाली जावा API है, और यह दस्तावेज़ हेरफेर और रूपांतरण के लिए कई प्रकार की सुविधाएँ प्रदान करता है।

## 1 परिचय
Aspose.Words for Java आपको Word दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इस ट्यूटोरियल में, हम उन्नत HTML दस्तावेज़ सहेजने के विकल्पों पर ध्यान केंद्रित करेंगे, जो आपको यह नियंत्रित करने में सक्षम बनाते हैं कि Word दस्तावेज़ HTML में कैसे परिवर्तित होते हैं।

## 2. राउंडट्रिप जानकारी निर्यात करें
`exportRoundtripInformation` विधि आपको राउंडट्रिप जानकारी को संरक्षित करते हुए Word दस्तावेज़ों को HTML में निर्यात करने की अनुमति देती है। यह जानकारी तब उपयोगी हो सकती है जब आप किसी भी दस्तावेज़-विशिष्ट विवरण को खोए बिना HTML को वापस Word प्रारूप में बदलना चाहते हैं।

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. फ़ॉन्ट्स को बेस64 के रूप में निर्यात करें
 साथ`exportFontsAsBase64` विधि, आप दस्तावेज़ में उपयोग किए गए फ़ॉन्ट को HTML में बेस 64-एन्कोडेड डेटा के रूप में निर्यात कर सकते हैं। यह सुनिश्चित करता है कि HTML प्रतिनिधित्व मूल Word दस्तावेज़ के समान फ़ॉन्ट शैलियों को बनाए रखता है।

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. संसाधन निर्यात करें
`exportResources` विधि आपको CSS स्टाइलशीट के प्रकार को निर्दिष्ट करने और फ़ॉन्ट संसाधनों को निर्यात करने की अनुमति देती है। आप HTML में संसाधनों के लिए एक संसाधन फ़ोल्डर और एक उपनाम भी सेट कर सकते हैं।

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://उदाहरण.com/संसाधन");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. मेटाफाइल्स को EMF या WMF में बदलें
`convertMetafilesToEmfOrWmf`यह विधि आपको दस्तावेज़ में मेटाफ़ाइल्स को EMF या WMF प्रारूप में परिवर्तित करने की अनुमति देती है, जिससे HTML में संगतता और सुचारू रेंडरिंग सुनिश्चित होती है।

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया है।
}
```

## 6. मेटाफ़ाइल्स को SVG में बदलें
 उपयोग`convertMetafilesToSvg` मेटाफ़ाइल्स को SVG फ़ॉर्मेट में बदलने की विधि। यह फ़ॉर्मेट HTML दस्तावेज़ों में वेक्टर ग्राफ़िक्स प्रदर्शित करने के लिए आदर्श है।

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया है।
}
```

## 7. CSS क्लास नाम उपसर्ग जोड़ें
 साथ`addCssClassNamePrefix` विधि, आप निर्यात किए गए HTML में CSS वर्ग नामों में उपसर्ग जोड़ सकते हैं। यह मौजूदा शैलियों के साथ टकराव को रोकने में मदद करता है।

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

## 8. MHTML संसाधनों के लिए CID URL निर्यात करें
`exportCidUrlsForMhtmlResources` MHTML प्रारूप में दस्तावेज़ों को सहेजते समय विधि का उपयोग किया जाता है। यह संसाधनों के लिए Content-ID URL निर्यात करने की अनुमति देता है।

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया है।
}
```

## 9. फ़ॉन्ट नाम हल करें
`resolveFontNames` यह विधि HTML प्रारूप में दस्तावेज़ों को सहेजते समय फ़ॉन्ट नामों को हल करने में मदद करती है, जिससे विभिन्न प्लेटफार्मों पर एक समान रेंडरिंग सुनिश्चित होती है।

```java
@Test
public void resolveFontNames() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया है।
}
```

## 10. टेक्स्ट इनपुट फॉर्म फ़ील्ड को टेक्स्ट के रूप में निर्यात करें
`exportTextInputFormFieldAsText` विधि फॉर्म फ़ील्ड को HTML में सादे पाठ के रूप में निर्यात करती है, जिससे उन्हें आसानी से पढ़ा और संपादित किया जा सकता है।

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // संक्षिप्तता के लिए कोड स्निपेट नहीं दिखाया गया है।
}
```

## 11. निष्कर्ष
इस ट्यूटोरियल में, हमने Aspose.Words द्वारा Java के लिए प्रदान किए गए उन्नत HTML दस्तावेज़ सहेजने के विकल्पों का पता लगाया। ये विकल्प आपको रूपांतरण प्रक्रिया पर बारीक नियंत्रण देते हैं, जिससे आप ऐसे HTML दस्तावेज़ बना सकते हैं जो मूल Word दस्तावेज़ों से काफ़ी मिलते-जुलते हों।

## 12. अक्सर पूछे जाने वाले प्रश्न
यहाँ Java और HTML दस्तावेज़ सहेजने के विकल्पों के लिए Aspose.Words के साथ काम करने के बारे में कुछ अक्सर पूछे जाने वाले प्रश्न दिए गए हैं:

### प्रश्न 1: मैं Java के लिए Aspose.Words का उपयोग करके HTML को वापस Word प्रारूप में कैसे परिवर्तित कर सकता हूं?
 HTML को वापस Word प्रारूप में बदलने के लिए, आप Aspose.Words API का उपयोग कर सकते हैं`load` HTML दस्तावेज़ को लोड करने और फिर उसे Word प्रारूप में सहेजने की विधि।

### प्रश्न 2: क्या मैं HTML में निर्यात करते समय CSS शैलियों को अनुकूलित कर सकता हूँ?
 हां, आप HTML में प्रयुक्त स्टाइलशीट को संशोधित करके या CSS स्टाइल को अनुकूलित कर सकते हैं।`addCssClassNamePrefix` सीएसएस वर्ग नामों में उपसर्ग जोड़ने की विधि।

### प्रश्न 3: क्या वेब प्रदर्शन के लिए HTML आउटपुट को अनुकूलित करने का कोई तरीका है?
हां, आप फ़ॉन्ट को बेस64 के रूप में निर्यात करने और मेटाफ़ाइल्स को SVG में परिवर्तित करने जैसे विकल्पों को कॉन्फ़िगर करके वेब डिस्प्ले के लिए HTML आउटपुट को अनुकूलित कर सकते हैं।

### प्रश्न 4: जटिल वर्ड दस्तावेज़ों को HTML में परिवर्तित करते समय क्या कोई सीमाएँ हैं?
जबकि Java के लिए Aspose.Words शक्तिशाली रूपांतरण क्षमताएं प्रदान करता है, जटिल लेआउट वाले जटिल Word दस्तावेज़ों को वांछित HTML आउटपुट प्राप्त करने के लिए अतिरिक्त पोस्ट-प्रोसेसिंग की आवश्यकता हो सकती है।
