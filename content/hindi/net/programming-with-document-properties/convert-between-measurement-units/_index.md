---
title: मापन इकाइयों के बीच कनवर्ट करें
linktitle: मापन इकाइयों के बीच कनवर्ट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ दस्तावेज़ में माप इकाइयों के बीच रूपांतरण के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-document-properties/convert-between-measurement-units/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words के साथ माप इकाइयों के बीच कनवर्ट करने के लिए C# स्रोत कोड के बारे में बताएंगे। यह सुविधा आपको माप की विभिन्न इकाइयों में मार्जिन, हेडर और फुटर दूरी आदि निर्दिष्ट करने की अनुमति देती है।

## चरण 1: प्रोजेक्ट सेटअप

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएं। सुनिश्चित करें कि आपके प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words का संदर्भ दिया गया है।

## चरण 2: दस्तावेज़ और कंस्ट्रक्टर बनाना

इस चरण में हम एक नया दस्तावेज़ बनाएंगे और कंस्ट्रक्टर को इनिशियलाइज़ करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: माप की इकाइयाँ कॉन्फ़िगर करें

अब हम माप की विभिन्न इकाइयों में मार्जिन, हेडर और फुटर दूरी आदि के मानों को परिवर्तित करेंगे। विशिष्ट माप इकाइयों में मान निर्दिष्ट करने के लिए निम्नलिखित कोड का उपयोग करें:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 यह कोड का उपयोग करता है`ConvertUtil` निर्दिष्ट मानों को इंच में परिवर्तित करने के लिए Aspose.Words का वर्ग (`InchToPoint` ). आप इसमें उपलब्ध अन्य रूपांतरण विधियों का भी उपयोग कर सकते हैं`ConvertUtil` मानों को अन्य माप इकाइयों में परिवर्तित करने के लिए वर्ग।

### .NET के लिए Aspose.Words का उपयोग करके मापन इकाइयों के बीच कनवर्ट करने के लिए उदाहरण स्रोत कोड

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मार्जिन, हेडर और फ़ूटर दूरी आदि निर्दिष्ट करते समय माप इकाइयों के बीच कैसे परिवर्तित किया जाए। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने दस्तावेज़ों में वांछित माप इकाइयों में मान आसानी से निर्दिष्ट कर सकते हैं।