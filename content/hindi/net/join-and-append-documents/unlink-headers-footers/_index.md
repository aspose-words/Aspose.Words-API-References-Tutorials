---
title: हेडर फ़ुटर अनलिंक करें
linktitle: हेडर फ़ुटर अनलिंक करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके हेडर और फूटर को अनलिंक करते हुए Word दस्तावेज़ों को जोड़ना और जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/unlink-headers-footers/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की अनलिंक हेडर्स फ़ुटर्स सुविधा का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। यह सुविधा आपको स्रोत दस्तावेज़ से हेडर और फ़ुटर्स को अनलिंक करते हुए Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है।

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

## चरण 3: स्रोत दस्तावेज़ में शीर्षलेख और पादलेख को अनलिंक करें

 स्रोत दस्तावेज़ में शीर्षलेखों और पादलेखों को गंतव्य दस्तावेज़ के शीर्षलेखों और पादलेखों से जारी रखने से अलग करने के लिए, आपको सेट करना होगा`LinkToPrevious` की संपत्ति`HeadersFooters` स्रोत दस्तावेज़ के पहले खंड में संग्रह`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित रहे।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को अनलिंक हेडर्स फ़ुटर्स सुविधा के साथ सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके हेडर फ़ुटर्स को अनलिंक करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके C# में "Unlink Headers Footers" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// इसे रोकने के लिए स्रोत दस्तावेज़ में शीर्षलेख और पादलेख को अनलिंक करें
	// गंतव्य दस्तावेज़ के शीर्षलेखों और पादलेखों को जारी रखने से रोकें।
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके अनलिंक हेडर फ़ुटर सुविधा को सफलतापूर्वक लागू कर दिया है। अंतिम दस्तावेज़ में गंतव्य दस्तावेज़ से अनलिंक किए गए स्रोत दस्तावेज़ के हेडर और फ़ुटर के साथ मर्ज की गई सामग्री होगी।