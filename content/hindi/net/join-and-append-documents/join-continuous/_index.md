---
title: निरंतर जुड़ें
linktitle: निरंतर जुड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके स्वरूपण को संरक्षित करते हुए दो दस्तावेज़ों को लगातार जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/join-continuous/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके दो दस्तावेज़ों को लगातार कैसे जोड़ा जाए। प्रदान किया गया स्रोत कोड दर्शाता है कि मूल स्वरूपण को बनाए रखते हुए किसी दस्तावेज़ को दूसरे दस्तावेज़ के अंत में कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- दस्तावेज़ निर्देशिका पथ जहाँ स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: स्रोत और गंतव्य दस्तावेज़ खोलें

 स्रोत और गंतव्य दस्तावेज़ों को खोलें`Document` क्लास कन्स्ट्रक्टर. बदलें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: निरंतर अनुभाग प्रारंभ सेट करें

स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ की सामग्री के ठीक बाद प्रदर्शित करने के लिए, सेट करें`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## चरण 4: स्रोत दस्तावेज़ जोड़ें

 स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें`AppendDocument` की विधि`Document` क्लास. आयात प्रारूप मोड को इस पर सेट करें`ImportFormatMode.KeepSourceFormatting` स्रोत दस्तावेज़ से मूल शैलियों को संरक्षित करने के लिए.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 5: संशोधित दस्तावेज़ को सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

इससे .NET के लिए Aspose.Words का उपयोग करके दो दस्तावेजों को लगातार जोड़ने का कार्यान्वयन पूरा हो जाता है।

### .NET के लिए Aspose.Words का उपयोग करके निरंतर जुड़ने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// दस्तावेज़ को गंतव्य दस्तावेज़ की सामग्री के ठीक बाद प्रदर्शित करें.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// स्रोत दस्तावेज़ में पाई गई मूल शैलियों का उपयोग करके स्रोत दस्तावेज़ को जोड़ें।
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```