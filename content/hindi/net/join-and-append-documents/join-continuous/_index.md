---
title: निरंतर जुड़ें
linktitle: निरंतर जुड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके फ़ॉर्मेटिंग को संरक्षित करते हुए लगातार दो दस्तावेज़ों को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/join-continuous/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके लगातार दो दस्तावेज़ों को कैसे जोड़ा जाए। प्रदान किया गया स्रोत कोड दर्शाता है कि मूल स्वरूपण को बनाए रखते हुए किसी दस्तावेज़ को दूसरे दस्तावेज़ के अंत में कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

-  .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहां स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: स्रोत और गंतव्य दस्तावेज़ खोलें

 का उपयोग करके स्रोत और गंतव्य दस्तावेज़ खोलें`Document` क्लास कंस्ट्रक्टर. प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: सतत अनुभाग प्रारंभ सेट करें

 स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ की सामग्री के ठीक बाद प्रदर्शित करने के लिए, सेट करें`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## चरण 4: स्रोत दस्तावेज़ जोड़ें

 का उपयोग करके स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें`AppendDocument` की विधि`Document` कक्षा। आयात प्रारूप मोड को इस पर सेट करें`ImportFormatMode.KeepSourceFormatting` स्रोत दस्तावेज़ से मूल शैलियों को संरक्षित करने के लिए।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: संशोधित दस्तावेज़ सहेजें

 अंत में, संशोधित गंतव्य दस्तावेज़ का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके लगातार दो दस्तावेज़ों को जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके लगातार जुड़ें के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// दस्तावेज़ को गंतव्य दस्तावेज़ सामग्री के ठीक बाद प्रदर्शित करें।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// स्रोत दस्तावेज़ में पाई गई मूल शैलियों का उपयोग करके स्रोत दस्तावेज़ जोड़ें।
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```