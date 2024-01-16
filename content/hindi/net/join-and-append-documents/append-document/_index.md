---
title: दस्तावेज़ संलग्न करें
linktitle: दस्तावेज़ संलग्न करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके एक दस्तावेज़ की सामग्री को दूसरे में जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/append-document/
---

यह ट्यूटोरियल बताता है कि एक दस्तावेज़ की सामग्री को दूसरे में जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि स्रोत और गंतव्य दस्तावेज़ों को कैसे खोलें, स्रोत दस्तावेज़ से अनुभागों को आयात करें और गंतव्य दस्तावेज़ में कैसे जोड़ें।

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

## चरण 3: स्रोत दस्तावेज़ से अनुभागों को गंतव्य दस्तावेज़ में जोड़ें

 स्रोत दस्तावेज़ में सभी अनुभागों के माध्यम से लूप करें और प्रत्येक अनुभाग को गंतव्य दस्तावेज़ में आयात करें`ImportNode` तरीका। फिर, आयातित अनुभाग को गंतव्य दस्तावेज़ में जोड़ें।

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## चरण 4: गंतव्य दस्तावेज़ सहेजें

 अंत में, संशोधित गंतव्य दस्तावेज़ का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके दस्तावेज़ संलग्न करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// स्रोत दस्तावेज़ में सभी अनुभागों को लूप करें।
	//अनुभाग नोड्स दस्तावेज़ नोड के तत्काल बच्चे हैं इसलिए हम केवल दस्तावेज़ की गणना कर सकते हैं।
	foreach (Section srcSection in srcDoc)
	{
		// क्योंकि हम एक अनुभाग को एक दस्तावेज़ से दूसरे दस्तावेज़ में कॉपी कर रहे हैं,
		// अनुभाग नोड को गंतव्य दस्तावेज़ में आयात करना आवश्यक है।
		// यह किसी दस्तावेज़-विशिष्ट संदर्भ को शैलियों, सूचियों आदि में समायोजित करता है।
		//
		// किसी नोड को आयात करने से मूल नोड की एक प्रति बन जाती है, लेकिन प्रतिलिपि
		// एसएस गंतव्य दस्तावेज़ में डालने के लिए तैयार है।
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// अब नए अनुभाग नोड को गंतव्य दस्तावेज़ में जोड़ा जा सकता है।
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```