---
title: वर्ड डॉक्यूमेंट में पैराग्राफ डालें
linktitle: वर्ड डॉक्यूमेंट में पैराग्राफ डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में पैराग्राफ़ सम्मिलित करना सीखें। निर्बाध दस्तावेज़ हेरफेर के लिए हमारे विस्तृत ट्यूटोरियल का अनुसरण करें।
type: docs
weight: 10
url: /hi/net/add-content-using-documentbuilder/insert-paragraph/
---
## परिचय

Word दस्तावेज़ों में प्रोग्रामेटिक रूप से पैराग्राफ सम्मिलित करने के लिए .NET के लिए Aspose.Words का उपयोग करने पर हमारी व्यापक मार्गदर्शिका में आपका स्वागत है। चाहे आप एक अनुभवी डेवलपर हों या .NET में दस्तावेज़ हेरफेर के साथ शुरुआत कर रहे हों, यह ट्यूटोरियल आपको स्पष्ट, चरण-दर-चरण निर्देशों और उदाहरणों के साथ प्रक्रिया से परिचित कराएगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- C# प्रोग्रामिंग और .NET फ्रेमवर्क का बुनियादी ज्ञान।
- आपकी मशीन पर विज़ुअल स्टूडियो स्थापित है।
-  .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/net/).

## नामस्थान आयात करें

सबसे पहले, आइए आरंभ करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using System.Drawing;
```

## चरण 1: दस्तावेज़ और दस्तावेज़बिल्डर को प्रारंभ करें

 अपना दस्तावेज़ सेट करके और प्रारंभ करके प्रारंभ करें`DocumentBuilder` वस्तु।
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: फ़ॉन्ट और पैराग्राफ को प्रारूपित करें

इसके बाद, नए पैराग्राफ के लिए फ़ॉन्ट और पैराग्राफ़ फ़ॉर्मेटिंग को कस्टमाइज़ करें।
```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## चरण 3: पैराग्राफ डालें

 अब, का उपयोग करके अपनी इच्छित सामग्री जोड़ें`WriteLn` उसकि विधि`DocumentBuilder`.
```csharp
builder.Writeln("A whole paragraph.");
```

## चरण 4: दस्तावेज़ सहेजें

अंत में, संशोधित दस्तावेज़ को अपने इच्छित स्थान पर सहेजें।
```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एक स्वरूपित पैराग्राफ सफलतापूर्वक सम्मिलित कर लिया है। यह प्रक्रिया आपको अपने एप्लिकेशन की आवश्यकताओं के अनुरूप गतिशील रूप से समृद्ध सामग्री उत्पन्न करने की अनुमति देती है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं .NET कोर अनुप्रयोगों के साथ .NET के लिए Aspose.Words का उपयोग कर सकता हूँ?
हाँ, .NET के लिए Aspose.Words .NET फ्रेमवर्क के साथ-साथ .NET कोर अनुप्रयोगों का समर्थन करता है।

### मैं .NET के लिए Aspose.Words के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### क्या Aspose.Words for .NET Microsoft Word संस्करणों के साथ संगत है?
हाँ, .NET के लिए Aspose.Words हालिया रिलीज़ सहित विभिन्न Microsoft Word संस्करणों के साथ संगतता सुनिश्चित करता है।

### क्या Aspose.Words for .NET दस्तावेज़ एन्क्रिप्शन का समर्थन करता है?
हां, आप .NET के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ों को प्रोग्रामेटिक रूप से एन्क्रिप्ट और सुरक्षित कर सकते हैं।

### मुझे .NET के लिए Aspose.Words के लिए अधिक सहायता और समर्थन कहां मिल सकता है?
 दौरा करना[Aspose.शब्द मंच](https://forum.aspose.com/c/words/8) सामुदायिक समर्थन और चर्चा के लिए।
