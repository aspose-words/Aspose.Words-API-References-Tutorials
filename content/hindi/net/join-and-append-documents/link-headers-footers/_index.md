---
title: लिंक हेडर फ़ुटर
linktitle: लिंक हेडर फ़ुटर
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय हेडर और फ़ुटर को लिंक करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/link-headers-footers/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की लिंक हेडर फ़ुटर सुविधा का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। यह सुविधा आपको स्रोत दस्तावेज़ के हेडर और फ़ुटर को गंतव्य दस्तावेज़ में पिछले अनुभाग से लिंक करते हुए कई वर्ड दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है।

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

## चरण 3: संलग्न दस्तावेज़ को नए पृष्ठ पर प्रदर्शित करने के लिए सेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ की सामग्री गंतव्य दस्तावेज़ में एक नए पृष्ठ पर दिखाई दे, आपको सेट करना होगा`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## चरण 4: हेडर और फ़ुटर को पिछले अनुभाग से लिंक करें

 स्रोत दस्तावेज़ के शीर्षलेखों और पादलेखों को गंतव्य दस्तावेज़ के पिछले अनुभाग से लिंक करने के लिए, आप इसका उपयोग कर सकते हैं`LinkToPrevious` की विधि`HeadersFooters` संग्रह.`true` पैरामीटर के रूप में, आप स्रोत दस्तावेज़ में किसी भी मौजूदा शीर्षलेख या पादलेख को ओवरराइड कर सकते हैं।

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित रहे।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को लिंक किए गए हेडर और फ़ुटर के साथ सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके लिंक हेडर फ़ुटर्स के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में "लिंक हेडर्स फ़ुटर्स" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// संलग्न दस्तावेज़ को नए पृष्ठ पर प्रदर्शित करने के लिए सेट करें.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// स्रोत दस्तावेज़ में शीर्षलेखों और पादलेखों को पिछले अनुभाग से लिंक करें।
	// यह स्रोत दस्तावेज़ में पहले से मौजूद किसी भी शीर्षलेख या पादलेख को ओवरराइड कर देगा।
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके लिंक हेडर फ़ुटर सुविधा को सफलतापूर्वक लागू कर दिया है। अंतिम दस्तावेज़ में गंतव्य दस्तावेज़ में पिछले अनुभाग से जुड़े स्रोत दस्तावेज़ से हेडर और फ़ुटर के साथ मर्ज की गई सामग्री शामिल होगी।