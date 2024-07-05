---
title: दस्तावेज़ को रिक्त स्थान में जोड़ें
linktitle: दस्तावेज़ को रिक्त स्थान में जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि Aspose.Words for .NET में किसी दस्तावेज़ को रिक्त गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/append-document-to-blank/
---

यह ट्यूटोरियल बताता है कि Aspose.Words for .NET का उपयोग करके एक दस्तावेज़ की सामग्री को रिक्त गंतव्य दस्तावेज़ में कैसे जोड़ा जाए। प्रदान किया गया स्रोत कोड दर्शाता है कि नया दस्तावेज़ कैसे बनाया जाए, उसकी सामग्री को कैसे हटाया जाए और फिर स्रोत दस्तावेज़ को उसमें कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- दस्तावेज़ निर्देशिका पथ जहाँ स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: नया गंतव्य दस्तावेज़ बनाएँ

 कोई नया बनाएं`Document` गंतव्य दस्तावेज़ के लिए ऑब्जेक्ट.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## चरण 3: गंतव्य दस्तावेज़ से मौजूदा सामग्री हटाएँ

 एक साफ़ गंतव्य दस्तावेज़ सुनिश्चित करने के लिए, दस्तावेज़ से सभी मौजूदा सामग्री को हटा दें`RemoveAllChildren` तरीका।

```csharp
dstDoc.RemoveAllChildren();
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 स्रोत दस्तावेज़ की सामग्री को गंतव्य दस्तावेज़ में जोड़ें`AppendDocument` विधि के साथ`ImportFormatMode.KeepSourceFormatting` विकल्प।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: गंतव्य दस्तावेज़ सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

इससे .NET के लिए Aspose.Words का उपयोग करके एक रिक्त गंतव्य दस्तावेज़ में एक दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा हो जाता है।

### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ को रिक्त में जोड़ने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// गंतव्य दस्तावेज़ रिक्त नहीं होता है, जिसके कारण अक्सर संलग्न दस्तावेज़ के सामने एक रिक्त पृष्ठ दिखाई देता है।
	// ऐसा इसलिए होता है क्योंकि मूल दस्तावेज़ में एक खंड रिक्त होता है और नया दस्तावेज़ अगले पृष्ठ पर शुरू होता है।
	// जोड़ने से पहले गंतव्य दस्तावेज़ से सारी सामग्री हटा दें।
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```