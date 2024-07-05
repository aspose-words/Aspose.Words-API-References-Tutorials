---
title: स्रोत को साथ रखें
linktitle: स्रोत को साथ रखें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि .NET के लिए Aspose.Words का उपयोग कैसे करें, ताकि स्रोत सामग्री को गंतव्य दस्तावेज़ के साथ रखते हुए Word दस्तावेज़ों को जोड़ा और जोड़ा जा सके।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/keep-source-together/
---

यह ट्यूटोरियल आपको Aspose.Words for .NET की Keep Source Together सुविधा का उपयोग करने की प्रक्रिया के बारे में बताएगा। यह सुविधा आपको स्रोत दस्तावेज़ की सामग्री को गंतव्य दस्तावेज़ की सामग्री के साथ रखते हुए कई Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है। 

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

## चरण 3: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ की सामग्री के बाद प्रदर्शित करने के लिए सेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ गंतव्य दस्तावेज़ की सामग्री के तुरंत बाद दिखाई दे, आपको सेट करना होगा`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## चरण 4: स्रोत दस्तावेज़ के लिए "अगले के साथ रखें" पैराग्राफ़ फ़ॉर्मेटिंग सेट करें

 स्रोत दस्तावेज़ में पैराग्राफ़ों को एक साथ रखने के लिए, आप दस्तावेज़ में प्रत्येक पैराग्राफ़ को दोहरा सकते हैं और सेट कर सकते हैं`KeepWithNext`संपत्ति को`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित रहे।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को "स्रोत को एक साथ रखें" सुविधा का उपयोग करके सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके Keep Source Together के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में "Keep Source Together" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ की सामग्री के ठीक बाद प्रदर्शित करने के लिए सेट करें।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके स्रोत को एक साथ रखने की सुविधा को सफलतापूर्वक लागू कर दिया है। अंतिम दस्तावेज़ में स्रोत दस्तावेज़ में पैराग्राफ़ के साथ मर्ज की गई सामग्री शामिल होगी।