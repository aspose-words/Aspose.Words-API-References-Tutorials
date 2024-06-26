---
title: मोटा पाठ्यांश
linktitle: मोटा पाठ्यांश
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: Aspose.Words for .NET चरण-दर-चरण मार्गदर्शिका के साथ टेक्स्ट को बोल्ड करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/bold-text/
---

इस उदाहरण में, हम आपको बताने जा रहे हैं कि .NET के लिए Aspose.Words के साथ टेक्स्ट को बोल्ड कैसे करें। बोल्ड टेक्स्ट इसे अधिक दृश्यमान बनाता है और इसे अधिक प्रमुखता देता है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: बोल्ड टेक्स्ट

 हम दस्तावेज़ बिल्डर की सेटिंग करके टेक्स्ट को बोल्ड कर सकते हैं`Font.Bold`संपत्ति को`true`.

```csharp
builder.Font.Bold = true;
```

## चरण 3: दस्तावेज़ में सामग्री जोड़ें

 अब हम दस्तावेज़ निर्माता विधियों का उपयोग करके दस्तावेज़ में सामग्री जोड़ सकते हैं, जैसे`Writeln`, जो पाठ की एक पंक्ति जोड़ता है।

```csharp
builder.Writeln("This text will be bold");
```

## .NET के लिए Aspose.Words का उपयोग करके बोल्ड टेक्स्ट के लिए उदाहरण स्रोत कोड


```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
DocumentBuilder builder = new DocumentBuilder();

// टेक्स्ट को बोल्ड बनाएं.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ टेक्स्ट को बोल्ड कैसे किया जाता है।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में टेक्स्ट को बोल्ड कैसे कर सकता हूँ?

 उत्तर: Aspose.Words में टेक्स्ट को बोल्ड बनाने के लिए, आप इसका उपयोग कर सकते हैं`Font.Bold` की संपत्ति`Run`वस्तु। आप इस प्रॉपर्टी को यहां सेट कर सकते हैं`true` विशिष्ट पाठ को बोल्ड करने के लिए. उदाहरण के लिए, आप उपयोग कर सकते हैं`run.Font.Bold=true` के अंदर टेक्स्ट को बोल्ड करने के लिए`Run` वस्तु।

#### प्रश्न: क्या एक ही पैराग्राफ में पाठ के कई हिस्सों को बोल्ड करना संभव है?

 उत्तर: हां, आप मल्टीपल का उपयोग करके एक ही पैराग्राफ में टेक्स्ट के कई टुकड़ों को बोल्ड कर सकते हैं`Run` वस्तुएं. आप एकाधिक बना सकते हैं`Run` ऑब्जेक्ट्स और सेट करें`Font.Bold`संपत्ति को`true` प्रत्येक ऑब्जेक्ट के लिए पाठ के वांछित भागों को बोल्ड करें। फिर आप उनका उपयोग करके पैराग्राफ में जोड़ सकते हैं`Paragraph.AppendChild(run)` तरीका।

#### प्रश्न: क्या मैं Aspose.Words में किसी तालिका या सेल में मौजूद टेक्स्ट को बोल्ड कर सकता हूं?

 उत्तर: हां, आप Aspose.Words में किसी तालिका या सेल में मौजूद टेक्स्ट को बोल्ड कर सकते हैं। आप उपयुक्त तरीकों का उपयोग करके अपने इच्छित सेल या पैराग्राफ पर नेविगेट कर सकते हैं और फिर बोल्ड फ़ॉर्मेटिंग लागू कर सकते हैं`Font.Bold` की संपत्ति`Run` या`Paragraph` वस्तु।