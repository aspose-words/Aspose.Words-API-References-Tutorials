---
title: जोड़ना
linktitle: जोड़ना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ लिंक सम्मिलित करना सीखें। चरण-दर-चरण मार्गदर्शिका.
type: docs
weight: 10
url: /hi/net/working-with-markdown/link/
---

इस उदाहरण में, हम आपको बताएंगे कि .NET के लिए Aspose.Words के साथ लिंक सुविधा का उपयोग कैसे करें। लिंक का उपयोग वेबसाइटों या अन्य दस्तावेज़ों के लिए क्लिक करने योग्य संदर्भ बनाने के लिए किया जाता है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: एक लिंक सम्मिलित करना

 हम इसका उपयोग करके एक लिंक डाल सकते हैं`Insertlink` दस्तावेज़ जनरेटर की विधि. हमें लिंक टेक्स्ट, यहां "एस्पोज़", साथ ही गंतव्य यूआरएल निर्दिष्ट करने की आवश्यकता है।

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", गलत);
```

### .NET के लिए Aspose.Words वाले लिंक के लिए उदाहरण स्रोत कोड


```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
DocumentBuilder builder = new DocumentBuilder();

// लिंक डालें.
builder.Insertlink("Aspose", "https://www.aspose.com", गलत);
```
बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ लिंक सुविधा का उपयोग कैसे करें।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में किसी URL से कैसे लिंक कर सकता हूं?

 उत्तर: Aspose.Words में किसी URL पते से लिंक करने के लिए, आप इसका उपयोग कर सकते हैं`<a>` के साथ टैग करें`href` यूआरएल पता युक्त विशेषता. उदाहरण के लिए, आप उपयोग कर सकते हैं`<a href="https://www.aspose.com">Click Here</a>` "यहां क्लिक करें" डिस्प्ले टेक्स्ट के साथ यूआरएल "https://www.example.com" पर हाइपरलिंक करने के लिए।

#### प्रश्न: क्या Aspose.Words में किसी आंतरिक बुकमार्क से लिंक करना संभव है?

 उत्तर: हाँ, Aspose.Words में किसी आंतरिक बुकमार्क से लिंक करना संभव है। आप इसका उपयोग कर सकते हैं`<a>` के साथ टैग करें`href` विशेषता जिसमें बुकमार्क का नाम हैश (#) से पहले होता है। उदाहरण के लिए,`<a href="#bookmark1">Go to bookmark 1</a>` दस्तावेज़ में "bookmark1" नामक बुकमार्क से लिंक हो जाएगा।

#### प्रश्न: मैं Aspose.Words में किसी लिंक के डिस्प्ले टेक्स्ट को कैसे अनुकूलित कर सकता हूं?

ए: Aspose.Words में किसी लिंक के डिस्प्ले टेक्स्ट को कस्टमाइज़ करने के लिए, आप बीच की सामग्री को संशोधित कर सकते हैं`<a>` टैग. उदाहरण के लिए,`<a href="https://www.aspose.com">Click here</a>` हाइपरलिंक के रूप में "यहां क्लिक करें" टेक्स्ट प्रदर्शित होगा।

#### प्रश्न: क्या मैं Aspose.Words में किसी लिंक के लिए लक्ष्य निर्दिष्ट कर सकता हूँ?

 उत्तर: हाँ, आप Aspose.Words का उपयोग करके किसी लिंक के लिए एक लक्ष्य निर्दिष्ट कर सकते हैं`target` की विशेषता`<a>` टैग। उदाहरण के लिए,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` लिंक एक नई विंडो या टैब में खुलेगा।