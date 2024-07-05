---
title: बिल्डर के साथ दस्तावेज़ सम्मिलित करें
linktitle: बिल्डर के साथ दस्तावेज़ सम्मिलित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके किसी अन्य दस्तावेज़ के अंत में दस्तावेज़ सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/insert-document-with-builder/
---

 यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को दूसरे दस्तावेज़ में कैसे सम्मिलित किया जाए।`DocumentBuilder` क्लास। प्रदान किया गया स्रोत कोड दर्शाता है कि स्रोत स्वरूपण को संरक्षित करते हुए किसी दस्तावेज़ को किसी अन्य दस्तावेज़ के अंत में कैसे सम्मिलित किया जाए।

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

## चरण 3: डॉक्यूमेंटबिल्डर को आरंभ करें

 एक नया उदाहरण बनाएँ`DocumentBuilder` क्लास में जाकर गंतव्य दस्तावेज़ को पैरामीटर के रूप में पास करें।

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## चरण 4: डॉक्यूमेंटबिल्डर को स्थान दें

चलाएं`DocumentBuilder` दस्तावेज़ के अंत तक`MoveToDocumentEnd` विधि। सम्मिलित दस्तावेज़ से मौजूदा सामग्री को अलग करने के लिए एक पृष्ठ विराम सम्मिलित करें।

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## चरण 5: स्रोत दस्तावेज़ डालें

 उपयोग`InsertDocument` की विधि`DocumentBuilder` स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में सम्मिलित करने के लिए क्लास। आयात प्रारूप मोड को इस पर सेट करें`ImportFormatMode.KeepSourceFormatting` स्रोत स्वरूपण को संरक्षित करने के लिए.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: संशोधित दस्तावेज़ को सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

इससे .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को दूसरे दस्तावेज़ में सम्मिलित करने का कार्यान्वयन पूरा हो जाता है।

### .NET के लिए Aspose.Words का उपयोग करके बिल्डर के साथ दस्तावेज़ सम्मिलित करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```