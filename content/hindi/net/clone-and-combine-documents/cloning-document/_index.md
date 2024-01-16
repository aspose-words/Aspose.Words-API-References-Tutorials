---
title: किसी वर्ड दस्तावेज़ को क्लोन करें
linktitle: किसी वर्ड दस्तावेज़ को क्लोन करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी शब्द दस्तावेज़ को क्लोन करना सीखें।
type: docs
weight: 10
url: /hi/net/clone-and-combine-documents/cloning-document/
---
इस ट्यूटोरियल में, हम आपको बताने जा रहे हैं कि .NET के लिए Aspose.Words की क्लोन सुविधा का उपयोग करके किसी वर्ड दस्तावेज़ को कैसे क्लोन किया जाए। स्रोत कोड को समझने और मौजूदा दस्तावेज़ की सटीक प्रतिलिपि बनाने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ लोड करना

आरंभ करने के लिए, अपनी दस्तावेज़ निर्देशिका निर्दिष्ट करें और मौजूदा दस्तावेज़ को दस्तावेज़ ऑब्जेक्ट में लोड करें। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## चरण 2: दस्तावेज़ को क्लोन करें

अब हम दस्तावेज़ की एक हूबहू प्रति बनाकर उसका क्लोन बनाने जा रहे हैं। ऐसे:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ क्लोनिंग के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words दस्तावेज़ क्लोन सुविधा का संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

इस कोड से आप .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ को क्लोन करने में सक्षम होंगे। दस्तावेज़ की सटीक प्रतिलिपि एक नए फ़ाइल नाम के अंतर्गत सहेजी जाएगी।


## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.Words की क्लोन सुविधा का उपयोग करके किसी Word दस्तावेज़ को कैसे क्लोन किया जाए। किसी मौजूदा दस्तावेज़ को लोड करके और क्लोन बनाकर, आप मूल को संशोधित किए बिना दस्तावेज़ की एक सटीक प्रतिलिपि बना सकते हैं। यह कार्यक्षमता तब मूल्यवान होती है जब आपको स्रोत फ़ाइल को प्रभावित किए बिना किसी दस्तावेज़ पर स्वतंत्र संचालन करने की आवश्यकता होती है। .NET के लिए Aspose.Words दस्तावेज़ों को क्लोन करने का एक सीधा तरीका प्रदान करता है, जिससे Word दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करना और दस्तावेज़ संस्करणों को प्रभावी ढंग से प्रबंधित करना आसान हो जाता है।

### किसी शब्द दस्तावेज़ को क्लोन करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ को क्लोन करने का उद्देश्य क्या है?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ को क्लोन करने से आप किसी मौजूदा दस्तावेज़ की सटीक प्रतिलिपि बना सकते हैं। यह सुविधा विशेष रूप से तब उपयोगी होती है जब आप नया संस्करण बनाते समय या मूल फ़ाइल को प्रभावित किए बिना आगे संशोधन करते समय मूल दस्तावेज़ की सामग्री और स्वरूपण को संरक्षित करना चाहते हैं।

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ को कैसे क्लोन कर सकता हूँ?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ को क्लोन करने के लिए, इन चरणों का पालन करें:
1.  मौजूदा दस्तावेज़ को दस्तावेज़ ऑब्जेक्ट में लोड करें`Document doc = new Document("file_path")`.
2.  का उपयोग करके दस्तावेज़ को क्लोन करें`Document clone = doc.Clone()`.
3.  का उपयोग करके क्लोन किए गए दस्तावेज़ को एक नई फ़ाइल में सहेजें`clone.Save("new_file_path")`.

#### प्रश्न: क्या मैं मूल दस्तावेज़ को प्रभावित किए बिना क्लोन किए गए दस्तावेज़ को संशोधित कर सकता हूँ?

उ: हां, क्लोन किया गया दस्तावेज़ मूल दस्तावेज़ से एक अलग उदाहरण है, और क्लोन में किए गए संशोधन मूल दस्तावेज़ को प्रभावित नहीं करेंगे। यह आपको स्रोत दस्तावेज़ में बदलाव किए बिना क्लोन किए गए दस्तावेज़ में सुरक्षित रूप से हेरफेर करने की अनुमति देता है।

#### प्रश्न: क्या एकाधिक दस्तावेज़ों का क्लोन बनाना और उन्हें एक ही दस्तावेज़ में संयोजित करना संभव है?

उत्तर: हां, आप क्लोन सुविधा का उपयोग करके कई दस्तावेज़ों को क्लोन कर सकते हैं और फिर आवश्यकतानुसार उन्हें एक ही दस्तावेज़ में संयोजित कर सकते हैं। एकाधिक दस्तावेज़ों को लोड और क्लोन करके, आप उनकी सामग्री को मर्ज कर सकते हैं और एक नया, एकीकृत दस्तावेज़ बना सकते हैं।