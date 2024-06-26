---
title: खुले प्रकार की विशेषताएँ
linktitle: खुले प्रकार की विशेषताएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words में ओपन टाइप सुविधाओं को सक्षम और उपयोग करने का तरीका जानें
type: docs
weight: 10
url: /hi/net/enable-opentype-features/open-type-features/
---

इस व्यापक ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words में ओपन टाइप सुविधाओं को कैसे सक्षम और उपयोग किया जाए। हम प्रक्रिया में आपका मार्गदर्शन करेंगे और आपको आवश्यक C# कोड स्निपेट प्रदान करेंगे। इस गाइड के अंत तक, आप अपने वर्ड दस्तावेज़ों में ओपन टाइप सुविधाओं के साथ काम करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर .NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल किया गया है।

## चरण 1: दस्तावेज़ लोड करें
प्रारंभ करने के लिए, दस्तावेज़ वर्ग का उपयोग करके दस्तावेज़ लोड करें:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## चरण 2: ओपन टाइप सुविधाएँ सक्षम करें
ओपन टाइप सुविधाओं को सक्षम करने के लिए, लेआउटऑप्शन क्लास की टेक्स्टशेपरफैक्ट्री प्रॉपर्टी को वांछित टेक्स्ट शेपर फैक्ट्री के उदाहरण पर सेट करें। इस उदाहरण में, हम HarfBuzzTextShaperFactory का उपयोग करते हैं:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## चरण 3: दस्तावेज़ सहेजें
ओपन टाइप सुविधाओं को सक्षम करने के बाद, दस्तावेज़ को वांछित आउटपुट प्रारूप में सहेजें, जैसे पीडीएफ:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### .NET के लिए Aspose.Words का उपयोग करके ओपन टाइप सुविधाओं के लिए उदाहरण स्रोत कोड
.NET के लिए Aspose.Words में ओपन टाइप सुविधाओं का उपयोग करने के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.Words में ओपन टाइप सुविधाओं को कैसे सक्षम और उपयोग किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, अब आप अपने वर्ड दस्तावेज़ों में ओपन टाइप सुविधाओं के साथ काम कर सकते हैं।

ओपन टाइप सुविधाएँ उन्नत टाइपोग्राफी और टेक्स्ट आकार देने की क्षमताएँ प्रदान करती हैं, जिससे आप देखने में आकर्षक और पेशेवर दिखने वाले दस्तावेज़ बना सकते हैं। विभिन्न टेक्स्ट शेपर फ़ैक्टरियों के साथ प्रयोग करें और अपनी परियोजनाओं में ओपन टाइप सुविधाओं की संभावनाओं का पता लगाएं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words में ओपनटाइप सुविधाओं को कैसे सक्षम करूं?

उ: .NET के लिए Aspose.Words में ओपनटाइप सुविधाओं को सक्षम करने के लिए, आपको ट्यूटोरियल में उल्लिखित चरणों का पालन करना होगा।

#### प्रश्न: .NET के लिए Aspose.Words में कौन सी ओपनटाइप सुविधाएँ समर्थित हैं?

उत्तर: .NET के लिए Aspose.Words कई ओपनटाइप सुविधाओं का समर्थन करता है, जैसे संयुक्ताक्षर, ग्लिफ़ विविधताएं, प्रासंगिक प्रतिस्थापन और बहुत कुछ।

#### प्रश्न: मैं कैसे जांच सकता हूं कि किसी विशिष्ट फ़ॉन्ट में ओपनटाइप सुविधा समर्थित है या नहीं?

उ: आप इसका उपयोग करके जांच सकते हैं कि किसी विशिष्ट फ़ॉन्ट में ओपनटाइप सुविधा समर्थित है या नहीं`Font.OpenTypeFeatures` .NET के लिए Aspose.Words में विधि।

#### प्रश्न: Aspose.Words for .NET किन अन्य टेक्स्ट फ़ॉर्मेटिंग सुविधाओं का समर्थन करता है?

उ: ओपनटाइप सुविधाओं के अलावा, .NET के लिए Aspose.Words अन्य टेक्स्ट फ़ॉर्मेटिंग सुविधाओं का भी समर्थन करता है जैसे पैराग्राफ़ फ़ॉर्मेट करना, तालिकाएँ बनाना, चित्र जोड़ना आदि।

#### प्रश्न: क्या मैं .NET के लिए Aspose.Words के सभी संस्करणों में ओपनटाइप सुविधाओं का उपयोग कर सकता हूं?

उत्तर: .NET के लिए Aspose.Words के नए संस्करणों में OpenType सुविधाएँ समर्थित हैं। सुनिश्चित करें कि आप इन सुविधाओं का लाभ उठाने के लिए एक संगत संस्करण का उपयोग कर रहे हैं।