---
title: DrawingML टेक्स्ट प्रभाव की जाँच करें
linktitle: DrawingML टेक्स्ट प्रभाव की जाँच करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: इस ट्यूटोरियल में, Aspose.Words for .NET के साथ Word दस्तावेज़ में DrawingML टेक्स्ट प्रभाव की जांच करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-fonts/check-drawingml-text-effect/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके Word दस्तावेज़ में DrawingML टेक्स्ट इफ़ेक्ट की जाँच करने का तरीका बताएँगे। DrawingML टेक्स्ट इफ़ेक्ट की जाँच करने से आप यह निर्धारित कर सकते हैं कि टेक्स्ट के किसी भाग पर कोई विशिष्ट इफ़ेक्ट लागू है या नहीं। हम आपको अपने .NET प्रोजेक्ट में कोड को समझने और लागू करने में मदद करने के लिए चरण-दर-चरण मार्गदर्शन करेंगे।

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित वस्तुएं हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है
- DrawingML टेक्स्ट प्रभाव युक्त एक वर्ड दस्तावेज़

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
 सबसे पहले, आपको अपने वर्ड डॉक्यूमेंट के स्थान के लिए डायरेक्टरी पथ सेट करना होगा।`"YOUR DOCUMENT DIRECTORY"` कोड में उचित पथ के साथ.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और पाठ प्रभाव की जाँच करें
इसके बाद, हम Word दस्तावेज़ को लोड करेंगे और दस्तावेज़ के मुख्य भाग के पहले पैराग्राफ़ में रन (वर्ण अनुक्रम) के संग्रह तक पहुँचेंगे। इसके बाद, हम जाँचेंगे कि क्या पहले रन के फ़ॉन्ट पर कोई विशिष्ट DrawingML टेक्स्ट प्रभाव लागू किया गया है।

```csharp
// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// DrawingML टेक्स्ट प्रभाव की जाँच करें
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### .NET के लिए Aspose.Words का उपयोग करके DMLText प्रभाव की जाँच के लिए नमूना स्रोत कोड 

```csharp

// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// एक रन में कई डीएमएल पाठ प्रभाव लागू हो सकते हैं।
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## निष्कर्ष
इस ट्यूटोरियल में, हमने देखा कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में DrawingML टेक्स्ट इफ़ेक्ट कैसे चेक करें। DrawingML टेक्स्ट इफ़ेक्ट चेक करने से आप टेक्स्ट के उन हिस्सों की पहचान कर सकते हैं जिन पर विशिष्ट इफ़ेक्ट लागू किए गए हैं। अपने Word दस्तावेज़ों में टेक्स्ट इफ़ेक्ट को बदलने और उनका विश्लेषण करने के लिए इस सुविधा का उपयोग करने में संकोच न करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words का उपयोग करके Word दस्तावेज़ में DrawingML टेक्स्ट प्रभाव तक कैसे पहुँच सकता हूँ?

उत्तर: Aspose.Words के साथ, आप दिए गए API का उपयोग करके Word दस्तावेज़ में DrawingML टेक्स्ट इफ़ेक्ट एक्सेस कर सकते हैं। आप टेक्स्ट एलिमेंट ब्राउज़ कर सकते हैं और टेक्स्ट इफ़ेक्ट के विशिष्ट गुणों, जैसे रंग, आकार आदि की जाँच कर सकते हैं।

#### प्रश्न: Word दस्तावेज़ों में सामान्यतः किस प्रकार के DrawingML पाठ प्रभाव का उपयोग किया जाता है?

उत्तर: Word दस्तावेज़ों में DrawingML टेक्स्ट प्रभावों के सामान्यतः उपयोग किए जाने वाले प्रकारों में छाया, प्रतिबिंब, चमक, ग्रेडिएंट आदि शामिल हैं। इन प्रभावों को टेक्स्ट की उपस्थिति और स्वरूपण में सुधार करने के लिए लागू किया जा सकता है।

#### प्रश्न: मैं वर्ड दस्तावेज़ में DrawingML टेक्स्ट प्रभाव का रंग कैसे जांच सकता हूं?

उत्तर: Word दस्तावेज़ में DrawingML टेक्स्ट इफ़ेक्ट का रंग जाँचने के लिए, आप टेक्स्ट इफ़ेक्ट के रंग गुणों तक पहुँचने के लिए Aspose.Words द्वारा प्रदान की गई विधियों का उपयोग कर सकते हैं। इस तरह आप विशिष्ट टेक्स्ट इफ़ेक्ट के लिए उपयोग किए जाने वाले रंग को प्राप्त कर सकते हैं।

#### प्रश्न: क्या एकाधिक अनुभागों वाले वर्ड दस्तावेज़ों में पाठ प्रभाव की जांच करना संभव है?

उत्तर: हाँ, Aspose.Words कई अनुभागों वाले Word दस्तावेज़ों में टेक्स्ट इफ़ेक्ट की जाँच करने की अनुमति देता है। आप दस्तावेज़ के प्रत्येक अनुभाग में नेविगेट कर सकते हैं और प्रत्येक अनुभाग के लिए टेक्स्ट इफ़ेक्ट को अलग-अलग एक्सेस कर सकते हैं।

#### प्रश्न: मैं वर्ड दस्तावेज़ में DrawingML टेक्स्ट प्रभाव की अपारदर्शिता की जांच कैसे कर सकता हूं?

उत्तर: Word दस्तावेज़ में DrawingML टेक्स्ट इफ़ेक्ट की अपारदर्शिता जाँचने के लिए, आप टेक्स्ट इफ़ेक्ट के अपारदर्शिता गुणों तक पहुँचने के लिए Aspose.Words द्वारा प्रदान की गई विधियों का उपयोग कर सकते हैं। यह आपको विशिष्ट टेक्स्ट इफ़ेक्ट पर लागू अपारदर्शिता मान प्राप्त करने की अनुमति देगा।