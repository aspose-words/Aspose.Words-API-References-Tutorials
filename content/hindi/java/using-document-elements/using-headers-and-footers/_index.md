---
title: जावा के लिए Aspose.Words में हेडर और फ़ुटर का उपयोग करना
linktitle: शीर्ष लेख और पाद लेख का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में हेडर और फ़ूटर का उपयोग कैसे करें, चरण-दर-चरण सीखें। सहजता से पेशेवर दस्तावेज़ बनाएं।
type: docs
weight: 16
url: /hi/java/using-document-elements/using-headers-and-footers/
---

इस व्यापक गाइड में, हम आपको जावा के लिए Aspose.Words में हेडर और फ़ुटर के साथ काम करने की प्रक्रिया के बारे में बताएंगे। दस्तावेज़ स्वरूपण में शीर्षलेख और पादलेख आवश्यक तत्व हैं, और Aspose.Words आपकी आवश्यकताओं के अनुसार उन्हें बनाने और अनुकूलित करने के लिए शक्तिशाली उपकरण प्रदान करता है।

अब, आइए इनमें से प्रत्येक चरण के बारे में विस्तार से जानें।

## 1. Aspose.शब्दों का परिचय

Aspose.Words एक शक्तिशाली जावा एपीआई है जो आपको Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, हेरफेर करने और प्रस्तुत करने की अनुमति देता है। यह हेडर और फ़ुटर सहित दस्तावेज़ स्वरूपण के लिए व्यापक सुविधाएँ प्रदान करता है।

## 2. अपना जावा वातावरण स्थापित करना

 इससे पहले कि आप Aspose.Words का उपयोग शुरू करें, सुनिश्चित करें कि आपने अपना जावा विकास वातावरण सही ढंग से सेट किया है। आप आवश्यक सेटअप निर्देश Aspose.Words दस्तावेज़ पृष्ठ पर पा सकते हैं:[Aspose.Words जावा दस्तावेज़ीकरण](https://reference.aspose.com/words/java/).

## 3. एक नया दस्तावेज़ बनाना

शीर्षलेख और पादलेख के साथ काम करने के लिए, आपको Aspose.Words का उपयोग करके एक नया दस्तावेज़ बनाना होगा। निम्नलिखित कोड दर्शाता है कि यह कैसे करना है:

```java
// नया दस्तावेज़ बनाने के लिए जावा कोड
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. पेज सेटअप को समझना

 आपके दस्तावेज़ के लेआउट को नियंत्रित करने के लिए पेज सेटअप महत्वपूर्ण है। आप इसका उपयोग करके शीर्षलेख और पादलेख से संबंधित विभिन्न गुण निर्दिष्ट कर सकते हैं`PageSetup` कक्षा। उदाहरण के लिए:

```java
// पृष्ठ गुण सेट करना
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. अलग-अलग प्रथम पृष्ठ शीर्षलेख/पाद लेख

Aspose.Words आपको अपने दस्तावेज़ के पहले पृष्ठ के लिए अलग-अलग शीर्षलेख और पादलेख रखने की अनुमति देता है। उपयोग`pageSetup.setDifferentFirstPageHeaderFooter(true);` इस सुविधा को सक्षम करने के लिए.

## 6. हेडर के साथ कार्य करना

### 6.1. हेडर में टेक्स्ट जोड़ना

 आप इसका उपयोग करके हेडर में टेक्स्ट जोड़ सकते हैं`DocumentBuilder`. यहाँ एक उदाहरण है:

```java
// प्रथम पृष्ठ शीर्षलेख में पाठ जोड़ना
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. हेडर में छवियाँ सम्मिलित करना

 हेडर में छवियाँ सम्मिलित करने के लिए, आप इसका उपयोग कर सकते हैं`insertImage` तरीका। यहाँ एक उदाहरण है:

```java
// हेडर में एक छवि सम्मिलित करना
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. हेडर शैलियों को अनुकूलित करना

जैसा कि ऊपर दिए गए उदाहरणों में दिखाया गया है, आप विभिन्न गुणों जैसे फ़ॉन्ट, संरेखण और बहुत कुछ सेट करके हेडर शैलियों को अनुकूलित कर सकते हैं।

## 7. फ़ुटर्स के साथ कार्य करना

### 7.1. फ़ुटर में टेक्स्ट जोड़ना

 हेडर के समान, आप इसका उपयोग करके फ़ुटर में टेक्स्ट जोड़ सकते हैं`DocumentBuilder`. यहाँ एक उदाहरण है:

```java
// प्राथमिक पादलेख में पाठ जोड़ना
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// आवश्यकतानुसार टेक्स्ट और फ़ील्ड डालें
```

### 7.2. फ़ुटर में छवियाँ सम्मिलित करना

 फ़ुटर में छवियाँ सम्मिलित करने के लिए, का उपयोग करें`insertImage` विधि, बिल्कुल हेडर की तरह।

### 7.3. फ़ुटर शैलियों को अनुकूलित करना

 का उपयोग करके पाद लेख शैलियों को अनुकूलित करें`DocumentBuilder`हेडर को अनुकूलित करने के समान।

## 8. पृष्ठ क्रमांकन

 आप जैसे फ़ील्ड का उपयोग करके अपने हेडर और फ़ूटर में पेज नंबर शामिल कर सकते हैं`PAGE` और`NUMPAGES`. जैसे ही आप पेज जोड़ते या हटाते हैं ये फ़ील्ड स्वचालित रूप से अपडेट हो जाती हैं।

## 9. फ़ुटर में कॉपीराइट जानकारी

अपने दस्तावेज़ के पाद लेख में कॉपीराइट जानकारी जोड़ने के लिए, आप दो कोशिकाओं वाली एक तालिका का उपयोग कर सकते हैं, एक को बाईं ओर और दूसरे को दाईं ओर संरेखित कर सकते हैं, जैसा कि कोड स्निपेट में दिखाया गया है।

## 10. अनेक अनुभागों के साथ कार्य करना

Aspose.Words आपको एक दस्तावेज़ के भीतर कई अनुभागों के साथ काम करने की अनुमति देता है। आप प्रत्येक अनुभाग के लिए अलग-अलग पेज सेटअप और हेडर/फुटर सेट कर सकते हैं।

## 11. लैंडस्केप ओरिएंटेशन

यदि आवश्यक हो तो आप विशिष्ट अनुभागों के ओरिएंटेशन को लैंडस्केप मोड में बदल सकते हैं।

## 12. पिछले अनुभागों से शीर्षलेख/पादलेख की प्रतिलिपि बनाना

पिछले अनुभागों से शीर्षलेख और पादलेख की प्रतिलिपि बनाने से जटिल दस्तावेज़ बनाते समय समय की बचत हो सकती है।

## 13. अपना दस्तावेज़ सहेजना

अपना दस्तावेज़ बनाने और अनुकूलित करने के बाद, इसका उपयोग करके इसे सहेजना न भूलें`doc.save()` तरीका।

## संपूर्ण स्रोत कोड
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // निर्दिष्ट करें कि क्या हम चाहते हैं कि पहले पृष्ठ के शीर्षलेख/पादलेख अन्य पृष्ठों से भिन्न हों।
        // निर्दिष्ट करने के लिए आप PageSetup.OddAndEvenPagesHeaderFooter प्रॉपर्टी का भी उपयोग कर सकते हैं
        // विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख/पादलेख।
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // हेडर के ऊपरी/बाएँ कोने में एक स्थित छवि डालें।
        // पृष्ठ के शीर्ष/बाएँ किनारों से दूरी 10 अंक पर सेट है।
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // हम पंक्ति पर पाठ का एक भाग (पृष्ठ क्रमांकन के साथ) बनाने के लिए दो कक्षों वाली एक तालिका का उपयोग करते हैं।
        // बाईं ओर संरेखित किया जाना है, और पाठ का दूसरा भाग (कॉपीराइट के साथ) दाईं ओर संरेखित किया जाना है।
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // यह वर्तमान पृष्ठ संख्या और कई पृष्ठों की स्वतः गणना करने के लिए PAGE और NUMPAGES फ़ील्ड का उपयोग करता है।
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // दूसरा पृष्ठ बनाने के लिए एक पृष्ठ विराम बनाएं जिस पर प्राथमिक शीर्षलेख/पादलेख दिखाई देंगे।
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // इस अनुभाग को किसी भिन्न प्रथम पृष्ठ शीर्षलेख/पाद लेख की आवश्यकता नहीं है, हमें दस्तावेज़ में केवल एक शीर्षक पृष्ठ की आवश्यकता है,
        //और इस पृष्ठ के लिए शीर्ष लेख/पाद लेख को पिछले अनुभाग में पहले ही परिभाषित किया जा चुका है।
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // यह अनुभाग पिछले अनुभाग के शीर्षलेख/पादलेख प्रदर्शित करता है
        // इस पृष्ठ की चौड़ाई को रद्द करने के लिए डिफ़ॉल्ट रूप से currentSection.HeadersFooters.LinkToPrevious(false) पर कॉल करें
        // नए अनुभाग के लिए अलग है, और इसलिए हमें पादलेख तालिका के लिए अलग-अलग सेल चौड़ाई निर्धारित करने की आवश्यकता है।
        currentSection.getHeadersFooters().linkToPrevious(false);
        // यदि हम इस सेक्शन के लिए पहले से मौजूद हेडर/फुटर सेट का उपयोग करना चाहते हैं।
        // लेकिन कुछ मामूली संशोधनों के साथ, हेडर/फुटर को कॉपी करना समीचीन हो सकता है
        // पिछले अनुभाग से और आवश्यक संशोधनों को वहां लागू करें जहां हम उन्हें चाहते हैं।
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
CopyHeadersFootersFromPreviousSection पद्धति का स्रोत कोड
```java
    /// <सारांश>
    /// क्लोन और कॉपी हेडर/फुटर निर्दिष्ट अनुभाग के पिछले अनुभाग का निर्माण करते हैं।
    ///</सारांश>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Words में हेडर और फ़ुटर के साथ काम करने की मूल बातें शामिल की हैं। आपने हेडर और फ़ुटर के साथ-साथ अन्य आवश्यक दस्तावेज़ फ़ॉर्मेटिंग तकनीकों को बनाना, अनुकूलित करना और स्टाइल करना सीख लिया है।

 अधिक विवरण और उन्नत सुविधाओं के लिए, देखें[Aspose.Words जावा दस्तावेज़ीकरण](https://reference.aspose.com/words/java/).

## पूछे जाने वाले प्रश्न

### 1. मैं अपने दस्तावेज़ के पाद लेख में पृष्ठ संख्याएँ कैसे जोड़ सकता हूँ?
 आप डालकर पेज नंबर जोड़ सकते हैं`PAGE` Aspose.Words का उपयोग करके पादलेख में फ़ील्ड डालें।

### 2. क्या Aspose.Words जावा विकास परिवेश के साथ संगत है?
हाँ, Aspose.Words जावा विकास के लिए समर्थन प्रदान करता है। सुनिश्चित करें कि आपके पास आवश्यक सेटअप मौजूद है।

### 3. क्या मैं शीर्षलेख और पादलेख के फ़ॉन्ट और शैली को अनुकूलित कर सकता हूँ?
बिल्कुल, आप अपने हेडर और फ़ूटर को दृश्यमान रूप से आकर्षक बनाने के लिए फ़ॉन्ट, संरेखण और अन्य शैलियों को अनुकूलित कर सकते हैं।

### 4. क्या विषम और सम पृष्ठों के लिए अलग-अलग शीर्षक रखना संभव है?
 हाँ, आप उपयोग कर सकते हैं`PageSetup.OddAndEvenPagesHeaderFooter` विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख निर्दिष्ट करने के लिए।

### 5. मैं जावा के लिए Aspose.Words के साथ कैसे शुरुआत करूं?
 आरंभ करने के लिए, पर जाएँ[Aspose.Words जावा दस्तावेज़ीकरण](https://reference.aspose.com/words/java/) एपीआई के उपयोग पर व्यापक मार्गदर्शन के लिए।