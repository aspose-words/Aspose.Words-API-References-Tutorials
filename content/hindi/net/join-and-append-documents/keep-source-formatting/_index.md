---
title: स्रोत स्वरूपण रखें
linktitle: स्रोत स्वरूपण रखें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके मूल स्वरूपण को संरक्षित करते हुए स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/keep-source-formatting/
---

यह ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.Words का उपयोग करके स्रोत दस्तावेज़ के मूल स्वरूपण को संरक्षित करते हुए स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहाँ स्रोत और गंतव्य दस्तावेज़ सहेजे जाएंगे.

## चरण 2: गंतव्य और स्रोत दस्तावेज़ बनाएँ

 के उदाहरण बनाएं`Document` गंतव्य और स्रोत दस्तावेज़ों के लिए.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## चरण 3: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 उपयोग`AppendDocument` स्रोत दस्तावेज़ को जोड़ने के लिए गंतव्य दस्तावेज़ की विधि।`ImportFormatMode.KeepSourceFormatting` स्रोत दस्तावेज़ के मूल स्वरूपण को बनाए रखने के लिए आयात प्रारूप मोड के रूप में।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 4: संशोधित दस्तावेज़ को सहेजें

 संशोधित दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करते हुए मूल स्वरूपण को बनाए रखते हुए स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके स्रोत स्वरूपण बनाए रखने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें.
	// स्रोत दस्तावेज़ को आयात करते समय उसके मूल स्वरूपण को बनाए रखने के लिए प्रारूप मोड पास करें।
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```