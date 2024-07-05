---
title: स्रोत हेडर फ़ुटर हटाएँ
linktitle: स्रोत हेडर फ़ुटर हटाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय हेडर और फ़ुटर को हटाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/remove-source-headers-footers/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की Remove Source Headers Footers सुविधा का उपयोग करने की प्रक्रिया के बारे में बताएगा। यह सुविधा आपको स्रोत दस्तावेज़ से हेडर और फ़ुटर हटाते समय Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है।

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

## चरण 3: स्रोत दस्तावेज़ अनुभागों से शीर्षलेख और पादलेख हटाएं

 स्रोत दस्तावेज़ में प्रत्येक अनुभाग से शीर्षलेख और पादलेख हटाने के लिए, आप एक का उपयोग करके अनुभागों के माध्यम से पुनरावृति कर सकते हैं`foreach` लूप और कॉल`ClearHeadersFooters` तरीका।

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## चरण 4: हेडरफुटर्स के लिए "LinkToPrevious" सेटिंग अक्षम करें

स्रोत दस्तावेज़ से शीर्षलेख और पादलेख साफ़ करने के बाद भी, यह संभावना है कि "LinkToPrevious" सेटिंग`HeadersFooters` अभी भी सेट किया जा सकता है। इस व्यवहार से बचने के लिए, आपको इसे स्पष्ट रूप से सेट करना होगा`false` प्रथम खंड के लिए`HeadersFooters` संपत्ति।

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित रहे।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को Remove Source Headers Footers सुविधा को सक्षम करके सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके स्रोत हेडर फ़ुटर्स को हटाने के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में "स्रोत हेडर फ़ुटर हटाएँ" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// स्रोत दस्तावेज़ के प्रत्येक अनुभाग से शीर्षलेख और पादलेख हटाएँ।
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// स्रोत दस्तावेज़ से शीर्षलेख और पादलेख साफ़ कर दिए जाने के बाद भी, "LinkToPrevious" सेटिंग
	// हेडर और फ़ुटर के लिए अभी भी सेट किया जा सकता है। इससे हेडर और फ़ुटर गंतव्य से जारी रहेंगे
	// इस व्यवहार से बचने के लिए इसे गलत पर सेट किया जाना चाहिए।
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
बस! आपने .NET के लिए Aspose.Words का उपयोग करके स्रोत हेडर फ़ुटर निकालें सुविधा को सफलतापूर्वक लागू कर दिया है। अंतिम दस्तावेज़ में स्रोत दस्तावेज़ से हटाए गए हेडर और फ़ुटर के साथ मर्ज की गई सामग्री होगी।