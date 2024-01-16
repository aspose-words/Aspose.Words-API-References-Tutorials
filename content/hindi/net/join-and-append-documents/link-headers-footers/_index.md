---
title: शीर्ष लेख पाद लेख लिंक करें
linktitle: शीर्ष लेख पाद लेख लिंक करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय हेडर और फ़ुटर को लिंक करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/link-headers-footers/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words के लिंक हेडर फ़ुटर्स सुविधा का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा। यह सुविधा आपको स्रोत दस्तावेज़ के शीर्षलेख और पादलेख को गंतव्य दस्तावेज़ में पिछले अनुभाग से जोड़ते हुए कई Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है।

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

 इसके बाद, आपको Aspose.Words का उपयोग करके स्रोत और गंतव्य दस्तावेज़ों को लोड करना होगा`Document` कक्षा। में फ़ाइल नाम अपडेट करें`Document` आपके दस्तावेज़ के नाम के अनुसार कंस्ट्रक्टर।

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: संलग्न दस्तावेज़ को एक नए पृष्ठ पर प्रदर्शित होने के लिए सेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ की सामग्री गंतव्य दस्तावेज़ में एक नए पृष्ठ पर दिखाई देती है, आपको सेट करने की आवश्यकता है`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## चरण 4: शीर्षलेख और पादलेख को पिछले अनुभाग से लिंक करें

स्रोत दस्तावेज़ के शीर्षलेख और पादलेख को गंतव्य दस्तावेज़ में पिछले अनुभाग से लिंक करने के लिए, आप इसका उपयोग कर सकते हैं`LinkToPrevious` की विधि`HeadersFooters` संग्रह। गुजरते हुए`true` पैरामीटर के रूप में, आप स्रोत दस्तावेज़ में किसी भी मौजूदा शीर्षलेख या पादलेख को ओवरराइड करते हैं।

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप इसका उपयोग करके स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` कक्षा।`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित है।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को लिंक किए गए हेडर और फ़ुटर के साथ सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके लिंक हेडर फ़ुटर के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में "लिंक हेडर फूटर" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// संलग्न दस्तावेज़ को एक नए पृष्ठ पर प्रदर्शित होने के लिए सेट करें।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// स्रोत दस्तावेज़ में शीर्षलेख और पादलेख को पिछले अनुभाग से लिंक करें।
	// यह स्रोत दस्तावेज़ में पहले से पाए गए किसी भी शीर्षलेख या पादलेख को ओवरराइड कर देगा।
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके लिंक हेडर फ़ुटर्स सुविधा को सफलतापूर्वक कार्यान्वित किया है। अंतिम दस्तावेज़ में गंतव्य दस्तावेज़ में पिछले अनुभाग से जुड़े स्रोत दस्तावेज़ से शीर्षलेख और पादलेख के साथ मर्ज की गई सामग्री शामिल होगी।