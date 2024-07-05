---
title: पेज लेआउट अपडेट करें
linktitle: पेज लेआउट अपडेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय पृष्ठ लेआउट को अपडेट करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/update-page-layout/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की अपडेट पेज लेआउट सुविधा का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। यह सुविधा सुनिश्चित करती है कि Word दस्तावेज़ों को जोड़ते और जोड़ते समय पेज लेआउट सही ढंग से अपडेट हो।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. Aspose.Words for .NET इंस्टॉल किया गया है। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं या NuGet के माध्यम से इंस्टॉल कर सकते हैं।
2. विजुअल स्टूडियो या कोई अन्य C# विकास वातावरण।

## चरण 1: दस्तावेज़ निर्देशिकाएँ आरंभ करें

 सबसे पहले, आपको अपने दस्तावेज़ निर्देशिका का पथ सेट करना होगा।`dataDir` चर को उस पथ पर जोड़ें जहां आपके दस्तावेज़ स्थित हैं.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत और गंतव्य दस्तावेज़ लोड करें

इसके बाद, आपको Aspose.Words का उपयोग करके स्रोत और गंतव्य दस्तावेज़ों को लोड करना होगा`Document` क्लास में फ़ाइल नाम अपडेट करें.`Document` अपने दस्तावेज़ के नाम के अनुसार कन्स्ट्रक्टर का चयन करें।

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: गंतव्य दस्तावेज़ के लिए पृष्ठ लेआउट अपडेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ को जोड़ने से पहले पृष्ठ लेआउट सही ढंग से अपडेट किया गया है, आप कॉल कर सकते हैं`UpdatePageLayout` गंतव्य दस्तावेज़ पर विधि.

```csharp
dstDoc.UpdatePageLayout();
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित रहे।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: पेज लेआउट को फिर से अपडेट करें

 स्रोत दस्तावेज़ को जोड़ने के बाद, आपको कॉल करने की आवश्यकता है`UpdatePageLayout`गंतव्य दस्तावेज़ पर विधि को पुनः चलाने से यह सुनिश्चित हो जाएगा कि परिशिष्ट ऑपरेशन के बाद किए गए कोई भी परिवर्तन प्रस्तुत आउटपुट में प्रतिबिंबित होंगे।

```csharp
dstDoc.UpdatePageLayout();
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को अपडेट पेज लेआउट सुविधा के साथ सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके पृष्ठ लेआउट अपडेट करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके C# में "अपडेट पेज लेआउट" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// यदि गंतव्य दस्तावेज़ को पीडीएफ, छवि आदि में प्रस्तुत किया गया है।
	// या UpdatePageLayout को स्रोत दस्तावेज़ से पहले बुलाया जाता है। जोड़ा जाता है,
	// उसके बाद किए गए कोई भी परिवर्तन रेंडर किए गए आउटपुट में प्रतिबिंबित नहीं होंगे
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// परिवर्तनों को रेंडर आउटपुट में अद्यतन करने के लिए, UpdatePageLayout को पुनः कॉल किया जाना चाहिए।
	// यदि इसे दोबारा नहीं बुलाया गया, तो संलग्न दस्तावेज़ अगले रेंडरिंग के आउटपुट में दिखाई नहीं देगा।
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके अपडेट पेज लेआउट सुविधा को सफलतापूर्वक लागू कर दिया है। अंतिम दस्तावेज़ में मर्ज की गई सामग्री होगी जिसमें पेज लेआउट सही ढंग से अपडेट किया गया होगा।