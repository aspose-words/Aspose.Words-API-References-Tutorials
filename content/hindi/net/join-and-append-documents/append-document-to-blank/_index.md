---
title: दस्तावेज़ को रिक्त स्थान पर जोड़ें
linktitle: दस्तावेज़ को रिक्त स्थान पर जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words में किसी दस्तावेज़ को रिक्त गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/append-document-to-blank/
---

यह ट्यूटोरियल बताता है कि एक दस्तावेज़ की सामग्री को रिक्त गंतव्य दस्तावेज़ में जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि एक नया दस्तावेज़ कैसे बनाया जाए, उसकी सामग्री को कैसे हटाया जाए, और फिर स्रोत दस्तावेज़ को उसमें कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

-  .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहां स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: एक नया गंतव्य दस्तावेज़ बनाएँ

 कोई नया बनाएं`Document` गंतव्य दस्तावेज़ के लिए ऑब्जेक्ट.

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## चरण 3: गंतव्य दस्तावेज़ से मौजूदा सामग्री हटाएँ

 एक स्वच्छ गंतव्य दस्तावेज़ सुनिश्चित करने के लिए, का उपयोग करके दस्तावेज़ से सभी मौजूदा सामग्री हटा दें`RemoveAllChildren` तरीका।

```csharp
dstDoc.RemoveAllChildren();
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 का उपयोग करके स्रोत दस्तावेज़ की सामग्री को गंतव्य दस्तावेज़ में जोड़ें`AppendDocument` विधि के साथ`ImportFormatMode.KeepSourceFormatting` विकल्प।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: गंतव्य दस्तावेज़ सहेजें

 अंत में, संशोधित गंतव्य दस्तावेज़ का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को रिक्त गंतव्य दस्तावेज़ में जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ को रिक्त स्थान में जोड़ने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// गंतव्य दस्तावेज़ खाली नहीं है, जिसके कारण अक्सर संलग्न दस्तावेज़ से पहले एक खाली पृष्ठ दिखाई देता है।
	// इसका कारण मूल दस्तावेज़ में एक खाली अनुभाग होना और नया दस्तावेज़ अगले पृष्ठ पर शुरू होना है।
	// जोड़ने से पहले गंतव्य दस्तावेज़ से सभी सामग्री हटा दें।
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```