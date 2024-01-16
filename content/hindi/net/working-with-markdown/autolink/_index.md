---
title: स्वत लिंक
linktitle: स्वत लिंक
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET चरण-दर-चरण मार्गदर्शिका के लिए Aspose.Words के साथ ऑटोलिंक सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/working-with-markdown/autolink/
---

इस उदाहरण में, हम बताएंगे कि .NET के लिए Aspose.Words के साथ "ऑटोलिंक" सुविधा का उपयोग कैसे करें। यह सुविधा आपको स्वचालित रूप से अपने दस्तावेज़ में हाइपरलिंक सम्मिलित करने की अनुमति देती है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## चरण 2: हाइपरलिंक सम्मिलित करना

 हम इसका उपयोग करके हाइपरलिंक सम्मिलित कर सकते हैं`InsertHyperlink` दस्तावेज़ जनरेटर की विधि. हम लिंक के लिए प्रदर्शित करने के लिए यूआरएल और टेक्स्ट निर्दिष्ट करते हैं।

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## चरण 3: एक लिंक के रूप में एक ईमेल पता सम्मिलित करना

हम "mailto:" उपसर्ग का उपयोग करके एक लिंक के रूप में एक ईमेल पता भी सम्मिलित कर सकते हैं। यह उपयोगकर्ताओं को अपने डिफ़ॉल्ट ईमेल क्लाइंट को खोलने के लिए लिंक पर क्लिक करने की अनुमति देगा।

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## चरण 4: दस्तावेज़ सहेजना

अंत में, हम दस्तावेज़ को वांछित प्रारूप में सहेज सकते हैं।

### .NET के लिए Aspose.Words का उपयोग करके ऑटोलिंक के लिए उदाहरण स्रोत कोड


```csharp
// दस्तावेज़ में सामग्री जोड़ने के लिए दस्तावेज़ निर्माता का उपयोग करें।
DocumentBuilder builder = new DocumentBuilder();

// हाइपरलिंक डालें।
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words के साथ "ऑटोलिंक" सुविधा का उपयोग कैसे करें।


### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं Aspose.Words में किसी URL पते के लिए स्वचालित लिंक कैसे बना सकता हूं?

उ: Aspose.Words में किसी URL पते के लिए एक स्वचालित लिंक बनाने के लिए, आप इसका उपयोग कर सकते हैं`<a>` के साथ टैग करें`href` यूआरएल पता युक्त विशेषता. उदाहरण के लिए, आप उपयोग कर सकते हैं`<a href="https://www.aspose.com">https://www.aspose.com</a>` स्वचालित रूप से "https://www.aspose.com" से लिंक करने के लिए।

#### प्रश्न: क्या Aspose.Words में स्वचालित लिंक के डिस्प्ले टेक्स्ट को कस्टमाइज़ करना संभव है?

 उ: हां, आप Aspose.Words में स्वचालित लिंक के प्रदर्शन टेक्स्ट को कस्टमाइज़ कर सकते हैं। यूआरएल पते को डिस्प्ले टेक्स्ट के रूप में उपयोग करने के बजाय, आप बीच की सामग्री को प्रतिस्थापित करके किसी अन्य टेक्स्ट का उपयोग कर सकते हैं`<a>` टैग. उदाहरण के लिए, आप उपयोग कर सकते हैं`<a href="https://www.aspose.com">Click here</a>` "यहां क्लिक करें" टेक्स्ट को स्वचालित लिंक के रूप में प्रदर्शित करने के लिए।

#### प्रश्न: मैं Aspose.Words में किसी ऑटोलिंक में अतिरिक्त विशेषताएँ कैसे जोड़ सकता हूँ?

 उत्तर: Aspose.Words में एक स्वचालित लिंक में अतिरिक्त विशेषताएँ जोड़ने के लिए, आप अंदर अतिरिक्त HTML विशेषताओं का उपयोग कर सकते हैं`<a>` टैग। उदाहरण के लिए, आप उपयोग कर सकते हैं`<a href="https://www.aspose.com" target="_blank">Link</a>` का उपयोग करके लिंक को एक नई विंडो या टैब में खोलने के लिए` attribute target="_blank"`.