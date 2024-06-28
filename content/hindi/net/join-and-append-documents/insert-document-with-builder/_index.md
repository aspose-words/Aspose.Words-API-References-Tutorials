---
title: बिल्डर के साथ दस्तावेज़ डालें
linktitle: बिल्डर के साथ दस्तावेज़ डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी अन्य दस्तावेज़ के अंत में दस्तावेज़ सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/insert-document-with-builder/
---

 यह ट्यूटोरियल बताता है कि किसी दस्तावेज़ को किसी अन्य दस्तावेज़ में सम्मिलित करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें`DocumentBuilder` कक्षा। प्रदान किया गया स्रोत कोड दर्शाता है कि स्रोत स्वरूपण को संरक्षित करते हुए किसी दस्तावेज़ को दूसरे दस्तावेज़ के अंत में कैसे सम्मिलित किया जाए।

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

## चरण 3: दस्तावेज़बिल्डर को प्रारंभ करें

 का एक नया उदाहरण बनाएं`DocumentBuilder` क्लास करें और गंतव्य दस्तावेज़ को एक पैरामीटर के रूप में पास करें।

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## चरण 4: दस्तावेज़बिल्डर को स्थिति दें

चलाएं`DocumentBuilder` का उपयोग करके दस्तावेज़ के अंत तक`MoveToDocumentEnd` तरीका। मौजूदा सामग्री को सम्मिलित दस्तावेज़ से अलग करने के लिए एक पृष्ठ विराम डालें।

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## चरण 5: स्रोत दस्तावेज़ डालें

 उपयोग`InsertDocument` की विधि`DocumentBuilder` स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में सम्मिलित करने के लिए क्लास। आयात प्रारूप मोड को इस पर सेट करें`ImportFormatMode.KeepSourceFormatting` स्रोत स्वरूपण को संरक्षित करने के लिए।

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: संशोधित दस्तावेज़ सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके एक दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके बिल्डर के साथ दस्तावेज़ सम्मिलित करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```