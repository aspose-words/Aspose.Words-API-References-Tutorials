---
title: पिछले अनुभाग से हेडर फ़ुटर कॉपी करें
linktitle: पिछले अनुभाग से हेडर फ़ुटर कॉपी करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में अनुभागों के बीच शीर्षलेख और पादलेख की प्रतिलिपि बनाना सीखें। यह विस्तृत मार्गदर्शिका निरंतरता और व्यावसायिकता सुनिश्चित करती है।
type: docs
weight: 10
url: /hi/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

अपने दस्तावेज़ों में शीर्षलेख और पादलेख जोड़ने और कॉपी करने से उनकी व्यावसायिकता और निरंतरता में काफी वृद्धि हो सकती है। .NET के लिए Aspose.Words के साथ, यह कार्य सीधा और उच्च अनुकूलन योग्य हो जाता है। इस व्यापक ट्यूटोरियल में, हम आपको चरण दर चरण आपके वर्ड दस्तावेज़ों में हेडर और फ़ुटर को एक अनुभाग से दूसरे अनुभाग में कॉपी करने की प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

-  .NET के लिए Aspose.Words: इसे यहां से डाउनलोड और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/words/net/).
- विकास परिवेश: जैसे कि विज़ुअल स्टूडियो, आपके C# कोड को लिखने और चलाने के लिए।
- C# का बुनियादी ज्ञान: C# प्रोग्रामिंग और .NET फ्रेमवर्क से परिचित।
- नमूना दस्तावेज़: या तो मौजूदा दस्तावेज़ का उपयोग करें या इस ट्यूटोरियल में दिखाए अनुसार एक नया दस्तावेज़ बनाएं।

## नामस्थान आयात करें

आरंभ करने के लिए, आपको आवश्यक नामस्थान आयात करने की आवश्यकता है जो आपको Aspose.Words कार्यक्षमताओं का उपयोग करने की अनुमति देगा।

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## चरण 1: एक नया दस्तावेज़ बनाएँ

 सबसे पहले, एक नया दस्तावेज़ बनाएं और a`DocumentBuilder` सामग्री को जोड़ने और हेरफेर की सुविधा के लिए।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: वर्तमान अनुभाग तक पहुंचें

इसके बाद, दस्तावेज़ के वर्तमान अनुभाग तक पहुंचें जहां आप शीर्षलेख और पादलेख की प्रतिलिपि बनाना चाहते हैं।

```csharp
Section currentSection = builder.CurrentSection;
```

## चरण 3: पिछले अनुभाग को परिभाषित करें

पिछले अनुभाग को परिभाषित करें जिसमें से आप शीर्षलेख और पादलेख की प्रतिलिपि बनाना चाहते हैं। यदि कोई पिछला अनुभाग नहीं है, तो आप बिना कोई कार्रवाई किए वापस लौट सकते हैं।

```csharp
Section previousSection = (Section)currentSection.PreviousSibling;
if (previousSection == null)
    return;
```

## चरण 4: मौजूदा शीर्षलेख और पादलेख साफ़ करें

दोहराव से बचने के लिए वर्तमान अनुभाग में किसी भी मौजूदा शीर्षलेख और पादलेख को साफ़ करें।

```csharp
currentSection.HeadersFooters.Clear();
```

## चरण 5: शीर्षलेख और पाद लेख कॉपी करें

पिछले अनुभाग से शीर्षलेख और पादलेख को वर्तमान अनुभाग में कॉपी करें। यह सुनिश्चित करता है कि प्रारूपण और सामग्री सभी अनुभागों में सुसंगत हैं।

```csharp
foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    currentSection.HeadersFooters.Add(headerFooter.Clone(true));
```

## चरण 6: दस्तावेज़ सहेजें

अंत में, दस्तावेज़ को वांछित स्थान पर सहेजें। यह चरण सुनिश्चित करता है कि आपके सभी परिवर्तन दस्तावेज़ फ़ाइल में लिखे गए हैं।

```csharp
doc.Save("OutputDocument.docx");
```

## प्रत्येक चरण का विस्तृत विवरण

### चरण 1: एक नया दस्तावेज़ बनाएँ

 इस चरण में, हम इसका एक नया उदाहरण प्रारंभ करते हैं`Document` कक्षा और ए`DocumentBuilder` .`DocumentBuilder` एक सहायक वर्ग है जो दस्तावेज़ में सामग्री जोड़ने की प्रक्रिया को सरल बनाता है।

### चरण 2: वर्तमान अनुभाग तक पहुंचें

हम वर्तमान अनुभाग का उपयोग करके पुनः प्राप्त करते हैं`builder.CurrentSection`. यह अनुभाग लक्ष्य होगा जहां हम पिछले अनुभाग से शीर्षलेख और पादलेख की प्रतिलिपि बनाएंगे।

### चरण 3: पिछले अनुभाग को परिभाषित करें

 जाँच करके`currentSection.PreviousSibling`, हम पिछला अनुभाग प्राप्त करते हैं। यदि पिछला अनुभाग शून्य है, तो विधि कोई और कार्रवाई किए बिना वापस आ जाती है। यह जाँच उन त्रुटियों को रोकती है जो पिछला अनुभाग न होने पर हो सकती हैं।

### चरण 4: मौजूदा शीर्षलेख और पादलेख साफ़ करें

हम यह सुनिश्चित करने के लिए वर्तमान अनुभाग में किसी भी मौजूदा हेडर और फ़ूटर को साफ़ करते हैं कि हमारे पास हेडर और फ़ुटर के कई सेट न हों।

### चरण 5: शीर्षलेख और पाद लेख कॉपी करें

 फ़ोरैच लूप का उपयोग करके, हम प्रत्येक के माध्यम से पुनरावृति करते हैं`HeaderFooter` पिछले अनुभाग में.`Clone(true)` विधि शीर्ष लेख या पाद लेख की एक गहरी प्रतिलिपि बनाती है, यह सुनिश्चित करती है कि इसकी सभी सामग्री और स्वरूपण संरक्षित हैं।

### चरण 6: दस्तावेज़ सहेजें

`doc.Save("OutputDocument.docx")` लाइन दस्तावेज़ में सभी परिवर्तन लिखती है, इसे निर्दिष्ट फ़ाइल नाम के साथ सहेजती है।

## निष्कर्ष

.NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में हेडर और फ़ुटर को एक सेक्शन से दूसरे सेक्शन में कॉपी करना सीधा और कुशल है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप यह सुनिश्चित कर सकते हैं कि आपके दस्तावेज़ सभी अनुभागों में एक सुसंगत और पेशेवर लुक बनाए रखें।

## पूछे जाने वाले प्रश्न

### Q1: .NET के लिए Aspose.Words क्या है?

.NET के लिए Aspose.Words एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों के भीतर Word दस्तावेज़ों को प्रोग्रामेटिक रूप से बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है।

### Q2: क्या मैं किसी अनुभाग से शीर्षलेख और पादलेख को दूसरे अनुभाग में कॉपी कर सकता हूँ?

हाँ, आप इस ट्यूटोरियल में वर्णित विधि का उपयोग करके किसी Word दस्तावेज़ में किसी भी अनुभाग के बीच शीर्षलेख और पादलेख की प्रतिलिपि बना सकते हैं।

### Q3: मैं विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पाद लेख कैसे संभाल सकता हूँ?

 आप इसका उपयोग करके विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख सेट कर सकते हैं`PageSetup.OddAndEvenPagesHeaderFooter` संपत्ति।

### Q4: मुझे .NET के लिए Aspose.Words के बारे में अधिक जानकारी कहां मिल सकती है?

 आप इस पर व्यापक दस्तावेज़ पा सकते हैं[Aspose.Words API दस्तावेज़ीकरण पृष्ठ](https://reference.aspose.com/words/net/).

### Q5: क्या .NET के लिए Aspose.Words का निःशुल्क परीक्षण उपलब्ध है?

हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[डाउनलोड पेज](https://releases.aspose.com/).