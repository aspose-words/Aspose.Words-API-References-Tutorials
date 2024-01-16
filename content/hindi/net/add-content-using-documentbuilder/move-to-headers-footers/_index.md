---
title: वर्ड दस्तावेज़ में हेडर फ़ुटर पर जाएँ
linktitle: वर्ड दस्तावेज़ में हेडर फ़ुटर पर जाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस चरण-दर-चरण मार्गदर्शिका के साथ सीखें कि Word दस्तावेज़ों में शीर्षलेख और पादलेख को नेविगेट करने और संशोधित करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/move-to-headers-footers/
---
इस उदाहरण में, हम .NET के लिए Aspose.Words के मूव टू हेडर्स फूटर्स फीचर का पता लगाएंगे। Aspose.Words एक शक्तिशाली दस्तावेज़ हेरफेर लाइब्रेरी है जो डेवलपर्स को Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और परिवर्तित करने की अनुमति देती है। हेडर/फ़ुटर में ले जाएँ सुविधा हमें दस्तावेज़ के भीतर विभिन्न हेडर और फ़ुटर पर नेविगेट करने और उनमें सामग्री जोड़ने में सक्षम बनाती है।

आइए .NET के लिए Aspose.Words का उपयोग करके मूव टू हेडर/फुटर्स सुविधा का उपयोग करने के तरीके को समझने के लिए चरण दर चरण स्रोत कोड पर जाएं।

## चरण 1: दस्तावेज़ और दस्तावेज़ निर्माता को आरंभ करना

सबसे पहले, दस्तावेज़ और दस्तावेज़बिल्डर ऑब्जेक्ट को प्रारंभ करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: शीर्षलेख और पाद लेख कॉन्फ़िगर करना

दस्तावेज़ के लिए शीर्ष लेख/पाद लेख सेटिंग निर्दिष्ट करें। इस उदाहरण में, हम पहले पेज और विषम/सम पेजों के लिए हेडर और फ़ूटर को अलग-अलग सेट करते हैं:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## चरण 3: विभिन्न पेजों के लिए हेडर बनाना

प्रत्येक हेडर प्रकार पर जाएँ और उनमें सामग्री जोड़ें। इस उदाहरण में, हम पहले पेज, यहां तक कि पेज और अन्य सभी पेजों के लिए हेडर बनाते हैं:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## चरण 4: दस्तावेज़ में पेज बनाना
एकाधिक पृष्ठ बनाने के लिए दस्तावेज़ में सामग्री जोड़ें। उदाहरण के लिए:

```csharp
// दस्तावेज़ में दो पेज बनाएं.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## चरण 5: दस्तावेज़ सहेजना

संशोधित दस्तावेज़ को वांछित स्थान पर सहेजें:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

उचित फ़ाइल पथ और प्रारूप (उदाहरण के लिए, DOCX) निर्दिष्ट करना सुनिश्चित करें।

### .NET के लिए Aspose.Words का उपयोग करके हेडर/फ़ुटर पर ले जाने के लिए उदाहरण स्रोत कोड

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// निर्दिष्ट करें कि हम पहले, सम और विषम पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख चाहते हैं।
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// हेडर बनाएं.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// दस्तावेज़ में दो पेज बनाएं.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## निष्कर्ष

इस उदाहरण में, हमने .NET के लिए Aspose.Words की मूव टू हेडर/फुटर्स सुविधा का पता लगाया। हमने सीखा कि Word दस्तावेज़ के भीतर विभिन्न शीर्षलेखों और पादलेखों पर कैसे नेविगेट करें और DocumentBuilder वर्ग का उपयोग करके उनमें सामग्री कैसे जोड़ें। यह सुविधा डेवलपर्स को विशिष्ट पृष्ठों या अनुभागों के लिए हेडर और फ़ुटर को अनुकूलित करने की अनुमति देती है, जिससे पेशेवर और संरचित दस्तावेज़ बनाने में लचीलापन मिलता है। .NET के लिए Aspose.Words Word दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए टूल का एक शक्तिशाली सेट प्रदान करता है, जिससे यह दस्तावेज़ प्रसंस्करण अनुप्रयोगों के लिए एक आवश्यक लाइब्रेरी बन जाता है।

### वर्ड दस्तावेज़ में हेडर फ़ुटर पर जाने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में मूव टू हेडर/फुटर्स सुविधा का उद्देश्य क्या है?

उत्तर: .NET के लिए Aspose.Words में हेडर/फ़ुटर की ओर जाने की सुविधा डेवलपर्स को एक Word दस्तावेज़ के भीतर विभिन्न हेडर और फ़ुटर पर नेविगेट करने और उनमें प्रोग्रामेटिक रूप से सामग्री जोड़ने की अनुमति देती है। यह तब उपयोगी होता है जब आपको दस्तावेज़ में विभिन्न पृष्ठों या अनुभागों के लिए शीर्षलेख और पादलेख को अनुकूलित करने की आवश्यकता होती है।

#### प्रश्न: क्या मैं दस्तावेज़ में विभिन्न पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख रख सकता हूँ?

उ: हाँ, आप क्रमशः PageSetup.DifferentFirstPageHeaderFooter और PageSetup.OddAndEvenPagesHeaderFooter गुणों का उपयोग करके पहले पृष्ठ, सम पृष्ठों और विषम पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख निर्दिष्ट कर सकते हैं।

#### प्रश्न: मैं विशिष्ट शीर्षलेखों और पादलेखों में सामग्री कैसे जोड़ सकता हूँ?

उ: विशिष्ट शीर्षलेखों और पादलेखों में सामग्री जोड़ने के लिए, DocumentBuilder वर्ग की MoveToHeaderFooter विधि का उपयोग करें। आप अपनी आवश्यकता के आधार पर हेडरफर्स्ट, हेडरईवन और हेडरप्राइमरी हेडर या फुटरफर्स्ट, फुटरईवन और फुटरप्राइमरी फुटर पर जा सकते हैं।

#### प्रश्न: क्या मैं दस्तावेज़ में किसी विशिष्ट अनुभाग के लिए शीर्षलेख और पादलेख बना सकता हूँ?

उत्तर: हाँ, आप दस्तावेज़ में किसी विशिष्ट अनुभाग में जाने के लिए DocumentBuilder वर्ग की MoveToSection विधि का उपयोग कर सकते हैं और फिर उस अनुभाग के भीतर शीर्षलेख और पादलेख बना सकते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके संशोधित दस्तावेज़ को फ़ाइल में कैसे सहेज सकता हूँ?

उ: आप दस्तावेज़ वर्ग की सेव विधि का उपयोग करके संशोधित दस्तावेज़ को वांछित स्थान और प्रारूप में सहेज सकते हैं। उचित फ़ाइल पथ और फ़ाइल प्रारूप (उदाहरण के लिए, DOCX) निर्दिष्ट करना सुनिश्चित करें।