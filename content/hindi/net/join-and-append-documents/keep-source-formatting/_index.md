---
title: सोर्स फ़ॉर्मेटिंग रखें
linktitle: सोर्स फ़ॉर्मेटिंग रखें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words का उपयोग करके मूल स्वरूपण को संरक्षित करते हुए किसी स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/keep-source-formatting/
---

यह ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.Words का उपयोग करके स्रोत दस्तावेज़ के मूल स्वरूपण को संरक्षित करते हुए किसी स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

-  .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहां स्रोत और गंतव्य दस्तावेज़ सहेजे जाएंगे।

## चरण 2: गंतव्य और स्रोत दस्तावेज़ बनाएं

 के उदाहरण बनाएँ`Document` गंतव्य और स्रोत दस्तावेज़ों के लिए।

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## चरण 3: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 उपयोग`AppendDocument` स्रोत दस्तावेज़ को जोड़ने के लिए गंतव्य दस्तावेज़ की विधि। उत्तीर्ण`ImportFormatMode.KeepSourceFormatting` स्रोत दस्तावेज़ के मूल स्वरूपण को बनाए रखने के लिए आयात प्रारूप मोड के रूप में।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 4: संशोधित दस्तावेज़ सहेजें

 का उपयोग करके संशोधित दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके मूल स्वरूपण को बनाए रखते हुए एक स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके स्रोत फ़ॉर्मेटिंग बनाए रखने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें।
	// स्रोत दस्तावेज़ को आयात करते समय उसके मूल स्वरूपण को बनाए रखने के लिए प्रारूप मोड पास करें।
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```