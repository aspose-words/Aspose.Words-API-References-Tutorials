---
title: सूची स्रोत स्वरूपण रखें
linktitle: सूची स्रोत स्वरूपण रखें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों को जोड़ते और जोड़ते समय सूची स्वरूपण को संरक्षित करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/list-keep-source-formatting/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की लिस्ट कीप सोर्स फ़ॉर्मेटिंग सुविधा का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। यह सुविधा आपको सूचियों के स्रोत फ़ॉर्मेटिंग को संरक्षित करते हुए Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है।

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## चरण 3: स्रोत दस्तावेज़ को निरंतर प्रवाह पर सेट करें

 यह सुनिश्चित करने के लिए कि गंतव्य दस्तावेज़ में जोड़े जाने पर स्रोत दस्तावेज़ की सामग्री निरंतर प्रवाहित होती रहे, आपको सेट करने की आवश्यकता है`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.KeepSourceFormatting`पैरामीटर यह सुनिश्चित करता है कि सूचियों के स्वरूपण सहित स्रोत स्वरूपण, परिशिष्ट ऑपरेशन के दौरान संरक्षित रहे।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को सूची रखें स्रोत स्वरूपण सुविधा का उपयोग करके सक्षम करके सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सूची स्रोत स्वरूपण के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में सूची रखें स्रोत स्वरूपण सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// दस्तावेज़ की सामग्री को इस प्रकार जोड़ें कि वह निरंतर प्रवाहित हो।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके सूची स्रोत स्वरूपण सुविधा को सफलतापूर्वक लागू किया है। अंतिम दस्तावेज़ में स्रोत दस्तावेज़ की सूची स्वरूपण संरक्षित के साथ मर्ज की गई सामग्री होगी।