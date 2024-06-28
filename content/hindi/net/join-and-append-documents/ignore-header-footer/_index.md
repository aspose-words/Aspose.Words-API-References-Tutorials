---
title: शीर्ष लेख पाद लेख पर ध्यान न दें
linktitle: शीर्ष लेख पाद लेख पर ध्यान न दें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके शीर्ष लेख और पाद लेख सामग्री को अनदेखा करते हुए दस्तावेज़ को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/ignore-header-footer/
---

यह ट्यूटोरियल बताता है कि शीर्ष लेख और पाद लेख सामग्री को अनदेखा करते हुए किसी दस्तावेज़ को जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि जोड़ने की प्रक्रिया के दौरान हेडर और फ़ूटर को बाहर करने के लिए आयात प्रारूप विकल्प कैसे सेट करें।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

-  .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहां स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: स्रोत और गंतव्य दस्तावेज़ खोलें

 का उपयोग करके स्रोत और गंतव्य दस्तावेज़ खोलें`Document` क्लास कंस्ट्रक्टर. प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: आयात प्रारूप विकल्प सेट करें

 का एक उदाहरण बनाएं`ImportFormatOptions` कक्षा और सेट करें`IgnoreHeaderFooter`संपत्ति को`false`. यह सुनिश्चित करता है कि शीर्ष लेख और पाद लेख सामग्री को जोड़ने की प्रक्रिया के दौरान शामिल किया गया है।

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 उपयोग`AppendDocument` स्रोत दस्तावेज़ को जोड़ने के लिए गंतव्य दस्तावेज़ की विधि। उत्तीर्ण`ImportFormatMode.KeepSourceFormatting`दूसरे पैरामीटर के रूप में और तीसरे पैरामीटर के रूप में आयात प्रारूप विकल्प।

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## चरण 5: गंतव्य दस्तावेज़ सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके शीर्ष लेख और पाद लेख सामग्री को अनदेखा करते हुए दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके हेडर फ़ूटर को अनदेखा करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```