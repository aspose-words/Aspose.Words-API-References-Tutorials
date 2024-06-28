---
title: पेज लेआउट अपडेट करें
linktitle: पेज लेआउट अपडेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय पेज लेआउट को अपडेट करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/update-page-layout/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की अपडेट पेज लेआउट सुविधा का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा। यह सुविधा सुनिश्चित करती है कि Word दस्तावेज़ों को जोड़ते और जोड़ते समय पेज लेआउट सही ढंग से अपडेट किया गया है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. .NET के लिए Aspose.Words स्थापित। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं या NuGet के माध्यम से इंस्टॉल कर सकते हैं।
2. विजुअल स्टूडियो या कोई अन्य C# विकास वातावरण।

## चरण 1: दस्तावेज़ निर्देशिकाएँ प्रारंभ करें

 सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। का मान संशोधित करें`dataDir` उस पथ के लिए परिवर्तनीय जहां आपके दस्तावेज़ स्थित हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत और गंतव्य दस्तावेज़ लोड करें

इसके बाद, आपको Aspose.Words का उपयोग करके स्रोत और गंतव्य दस्तावेज़ों को लोड करना होगा।`Document` कक्षा। में फ़ाइल नाम अपडेट करें`Document` आपके दस्तावेज़ के नाम के अनुसार कंस्ट्रक्टर।

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: गंतव्य दस्तावेज़ के लिए पेज लेआउट अपडेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ को जोड़ने से पहले पेज लेआउट सही ढंग से अपडेट किया गया है, आप कॉल कर सकते हैं`UpdatePageLayout` गंतव्य दस्तावेज़ पर विधि.

```csharp
dstDoc.UpdatePageLayout();
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप इसका उपयोग करके स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` कक्षा।`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित है।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: पेज लेआउट को दोबारा अपडेट करें

 स्रोत दस्तावेज़ को जोड़ने के बाद, आपको कॉल करना होगा`UpdatePageLayout`यह सुनिश्चित करने के लिए कि एपेंड ऑपरेशन के बाद किए गए कोई भी परिवर्तन प्रस्तुत आउटपुट में प्रतिबिंबित होते हैं, गंतव्य दस्तावेज़ पर फिर से विधि।

```csharp
dstDoc.UpdatePageLayout();
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, अपडेट पेज लेआउट सुविधा का उपयोग करके मर्ज किए गए दस्तावेज़ को सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके अपडेट पेज लेआउट के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके C# में "अपडेट पेज लेआउट" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// यदि गंतव्य दस्तावेज़ को पीडीएफ, छवि इत्यादि में प्रस्तुत किया गया है।
	// या UpdatePageLayout को स्रोत दस्तावेज़ से पहले कॉल किया जाता है। संलग्न है,
	// उसके बाद किया गया कोई भी परिवर्तन प्रस्तुत आउटपुट में प्रतिबिंबित नहीं होगा
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// रेंडर किए गए आउटपुट में परिवर्तनों को अद्यतन करने के लिए, UpdatePageLayout को फिर से कॉल किया जाना चाहिए।
	// यदि दोबारा नहीं बुलाया गया, तो संलग्न दस्तावेज़ अगले रेंडरिंग के आउटपुट में दिखाई नहीं देगा।
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपडेट पेज लेआउट सुविधा को सफलतापूर्वक कार्यान्वित किया है। अंतिम दस्तावेज़ में पेज लेआउट को सही ढंग से अपडेट करने के साथ मर्ज की गई सामग्री शामिल होगी।