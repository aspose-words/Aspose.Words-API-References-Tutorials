---
title: पीडीएफ दस्तावेज़ में यूआरआई से बचें
linktitle: पीडीएफ दस्तावेज़ में यूआरआई से बचें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: चरण-दर-चरण मार्गदर्शिका, .NET के लिए Aspose.Words के साथ पीडीएफ दस्तावेज़ में URI से कैसे बचें।
type: docs
weight: 10
url: /hi/net/programming-with-pdfsaveoptions/escape-uri/
---

यह आलेख .NET के लिए Aspose.Words के साथ PDF दस्तावेज़ में URI से बचने के बारे में चरण-दर-चरण मार्गदर्शिका प्रदान करता है। हम कोड के प्रत्येक भाग को विस्तार से समझाएंगे। इस ट्यूटोरियल के अंत में, आप यह समझ पाएंगे कि किसी दस्तावेज़ में एस्केप्ड उरी के साथ हाइपरलिंक कैसे सम्मिलित करें।

शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words को स्थापित और कॉन्फ़िगर किया है। आप Aspose वेबसाइट पर लाइब्रेरी और इंस्टॉलेशन निर्देश पा सकते हैं।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें

 आरंभ करने के लिए, आपको उस निर्देशिका का पथ परिभाषित करना होगा जहां आपके दस्तावेज़ स्थित हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और एक DocumentBuilder बनाएँ

 इसके बाद, हमें एक नया बनाने की जरूरत है`Document` वस्तु और ए`DocumentBuilder` दस्तावेज़ बनाने के लिए ऑब्जेक्ट।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: बची हुई उरी के साथ हाइपरलिंक डालें

 उपयोग`InsertHyperlink` की विधि`DocumentBuilder` दस्तावेज़ में हाइपरलिंक सम्मिलित करने के लिए ऑब्जेक्ट। का उपयोग करके उरी से बचना होगा`Uri.EscapeUriString` प्रारूप त्रुटियों से बचने के लिए कार्य।

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), गलत);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), गलत);
```

## चरण 4: दस्तावेज़ को पीडीएफ के रूप में सहेजें

 अंत में, हम इसका उपयोग करके दस्तावेज़ को पीडीएफ के रूप में सहेज सकते हैं`Save` की विधि`Document` वस्तु। आउटपुट फ़ाइल नाम निर्दिष्ट करें.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

बस इतना ही ! आपने .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ में बची हुई Uri के साथ हाइपरलिंक सफलतापूर्वक सम्मिलित कर दिए हैं।

### .NET के लिए Aspose.Words के साथ उरी से बचने का नमूना स्रोत कोड


```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words का उपयोग करके PDF दस्तावेज़ में URI से बचने का तरीका बताया। यूआरआई से बचकर, आप फ़ॉर्मेटिंग त्रुटियों से बच सकते हैं और यह सुनिश्चित कर सकते हैं कि हाइपरलिंक की सही व्याख्या की गई है और पीडीएफ दस्तावेज़ में प्रदर्शित किया गया है। अपने पीडीएफ दस्तावेज़ में एस्केप्ड यूआरआई के साथ हाइपरलिंक डालने के लिए बताए गए चरणों का पालन करें। बचना सुनिश्चित करें.

### अक्सर पूछे जाने वाले प्रश्नों

#### प्रश्न: पीडीएफ दस्तावेज़ में एस्केप यूआरआई क्या है और यह महत्वपूर्ण क्यों है?
उ: पीडीएफ दस्तावेज़ में एस्केप यूआरआई प्रारूप त्रुटियों से बचने के लिए यूआरएल में विशेष वर्णों को एस्केप अनुक्रमों में परिवर्तित करने की विधि को संदर्भित करता है। यह महत्वपूर्ण है क्योंकि URL में विशेष वर्ण URL की संरचना को बाधित कर सकते हैं और गलत व्याख्या या गलत प्रतिपादन का कारण बन सकते हैं। विशेष वर्णों से बचकर, हम गारंटी देते हैं कि यूआरएल की सही व्याख्या की गई है और पीडीएफ दस्तावेज़ में प्रदर्शित किया गया है।

#### प्रश्न: पीडीएफ दस्तावेज़ में यूआरआई से बचने के लिए मैं .NET के लिए Aspose.Words का उपयोग कैसे कर सकता हूं?
उ: .NET के लिए Aspose.Words का उपयोग करके PDF दस्तावेज़ में URI से बचने के लिए, इन चरणों का पालन करें:

 प्रतिस्थापित करके वह निर्देशिका पथ सेट करें जहां आपके दस्तावेज़ स्थित हैं`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` दस्तावेज़ बनाने के लिए ऑब्जेक्ट।

 उपयोग`InsertHyperlink` की विधि`DocumentBuilder` दस्तावेज़ में हाइपरलिंक सम्मिलित करने के लिए ऑब्जेक्ट। का उपयोग करके यूआरआई से बचना सुनिश्चित करें`Uri.EscapeUriString` प्रारूप त्रुटियों से बचने के लिए कार्य।

 उपयोग`Save` की विधि`Document` आउटपुट फ़ाइल का नाम निर्दिष्ट करके दस्तावेज़ को पीडीएफ प्रारूप में सहेजने के लिए ऑब्जेक्ट।

#### प्रश्न: पीडीएफ दस्तावेज़ में यूआरआई से बचने के क्या फायदे हैं?
उ: पीडीएफ दस्तावेज़ में यूआरआई से बचने के लाभ हैं:

प्रारूप त्रुटियों की रोकथाम: यूआरआई एस्केपिंग यूआरएल में विशेष वर्णों के कारण होने वाली प्रारूप त्रुटियों को रोकने में मदद करता है, यह सुनिश्चित करता है कि यूआरएल की सही व्याख्या की गई है और पीडीएफ दस्तावेज़ में प्रदर्शित किया गया है।

पीडीएफ पाठकों के साथ संगतता: एस्केप्ड यूआरआई आमतौर पर पीडीएफ पाठकों द्वारा अच्छी तरह से समर्थित होते हैं, जिससे बेहतर संगतता और लगातार उपयोगकर्ता अनुभव सुनिश्चित होता है।

#### प्रश्न: यूआरआई में किन विशेष वर्णों से बचना चाहिए?
 ए: यूआरआई में जिन विशेष वर्णों से बचना चाहिए वे हैं: स्पेस, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.