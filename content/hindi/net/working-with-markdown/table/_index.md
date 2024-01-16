---
title: मेज़
linktitle: मेज़
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET चरण-दर-चरण मार्गदर्शिका के लिए Aspose.Words के साथ तालिका बनाना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/table/
---


इस उदाहरण में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका बनाने का तरीका बताएंगे। तालिका एक डेटा संरचना है जो जानकारी को पंक्तियों और स्तंभों में व्यवस्थित करती है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## चरण 2: सेल और डेटा जोड़ें

 हम इसका उपयोग करके अपनी तालिका में सेल और डेटा जोड़ेंगे`InsertCell` विधि और`Writeln` दस्तावेज़ जनरेटर की विधि.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### .NET के लिए Aspose.Words के साथ एक तालिका बनाने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
DocumentBuilder builder = new DocumentBuilder();

// पहली पंक्ति जोड़ें.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// दूसरी पंक्ति जोड़ें.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ एक तालिका कैसे बनाई जाती है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं मार्कडाउन में एक तालिका कैसे बनाऊं?

ए: मार्कडाउन में एक तालिका बनाने के लिए, पाइप के सिंटैक्स का उपयोग करें (`|`कोशिकाओं और डैश को परिसीमित करने के लिए (`-`) टेबल हेडर को परिसीमित करने के लिए।

#### प्रश्न: क्या हम मार्कडाउन में किसी तालिका के स्वरूप को अनुकूलित कर सकते हैं?

ए: मानक मार्कडाउन में, तालिका अनुकूलन विकल्प सीमित हैं। हालाँकि, कुछ मार्कडाउन संपादक आपको तालिकाओं के स्वरूप को अनुकूलित करने के लिए सीएसएस शैलियों को जोड़ने की अनुमति देते हैं।

#### प्रश्न: मार्कडाउन में किसी तालिका में सेल्स को कैसे मर्ज किया जाए?

उ: मार्कडाउन में किसी तालिका में कोशिकाओं को मर्ज करना उपयोग किए गए मार्कडाउन संपादक पर निर्भर करता है। कुछ मार्कडाउन संपादक एक विशिष्ट सिंटैक्स का उपयोग करके कोशिकाओं को मर्ज करने का समर्थन करते हैं।

#### प्रश्न: क्या मार्कडाउन में टेबल सीएसएस स्टाइल का समर्थन करते हैं?

उ: मानक मार्कडाउन में, टेबल सीएसएस शैलियों के लिए प्रत्यक्ष समर्थन प्रदान नहीं करते हैं। हालाँकि, कुछ मार्कडाउन संपादक आपको तालिकाओं के स्वरूप को अनुकूलित करने के लिए सीएसएस शैलियों को जोड़ने की अनुमति देते हैं।

#### प्रश्न: क्या हम मार्कडाउन में किसी तालिका के कक्षों में इनलाइन प्रारूप में लिंक या टेक्स्ट जोड़ सकते हैं?

उ: हां, आप उपयुक्त मार्कडाउन सिंटैक्स का उपयोग करके मार्कडाउन में तालिका कोशिकाओं में लिंक या इनलाइन टेक्स्ट जोड़ सकते हैं।