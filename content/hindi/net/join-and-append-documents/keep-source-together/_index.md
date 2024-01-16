---
title: स्रोत को एक साथ रखें
linktitle: स्रोत को एक साथ रखें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: स्रोत सामग्री को गंतव्य दस्तावेज़ के साथ रखते हुए Word दस्तावेज़ों को जोड़ने और जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/keep-source-together/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की कीप सोर्स टुगेदर सुविधा का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा। यह सुविधा आपको स्रोत दस्तावेज़ की सामग्री को गंतव्य दस्तावेज़ की सामग्री के साथ रखते हुए कई Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है। 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## चरण 3: गंतव्य दस्तावेज़ की सामग्री के बाद स्रोत दस्तावेज़ को प्रदर्शित करने के लिए सेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ गंतव्य दस्तावेज़ की सामग्री के तुरंत बाद दिखाई देता है, आपको सेट करने की आवश्यकता है`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## चरण 4: स्रोत दस्तावेज़ के लिए "अगले के साथ रखें" पैराग्राफ फ़ॉर्मेटिंग सेट करें

स्रोत दस्तावेज़ में अनुच्छेदों को एक साथ रखने के लिए, आप दस्तावेज़ में प्रत्येक अनुच्छेद को दोहरा सकते हैं और सेट कर सकते हैं`KeepWithNext`संपत्ति को`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप इसका उपयोग करके स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` कक्षा।`ImportFormatMode.KeepSourceFormatting` पैरामीटर यह सुनिश्चित करता है कि एपेंड ऑपरेशन के दौरान स्रोत स्वरूपण संरक्षित है।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

 अंत में, मर्ज किए गए दस्तावेज़ को "कीप सोर्स टुगेदर" सुविधा का उपयोग करके सक्षम करके सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके स्रोत को एक साथ रखें के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में "कीप सोर्स टुगेदर" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ की सामग्री के ठीक बाद प्रदर्शित होने के लिए सेट करें।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके कीप सोर्स टुगेदर सुविधा को सफलतापूर्वक कार्यान्वित किया है। अंतिम दस्तावेज़ में स्रोत दस्तावेज़ के पैराग्राफों के साथ मर्ज की गई सामग्री शामिल होगी।