---
title: हेडर फ़ुटर को अनदेखा करें
linktitle: हेडर फ़ुटर को अनदेखा करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके हेडर और फ़ुटर सामग्री को अनदेखा करते हुए दस्तावेज़ को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/ignore-header-footer/
---

यह ट्यूटोरियल बताता है कि हेडर और फ़ुटर सामग्री को अनदेखा करते हुए दस्तावेज़ को जोड़ने के लिए Aspose.Words for .NET का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि जोड़ने की प्रक्रिया के दौरान हेडर और फ़ुटर को बाहर करने के लिए आयात प्रारूप विकल्पों को कैसे सेट किया जाए।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- दस्तावेज़ निर्देशिका पथ जहाँ स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: स्रोत और गंतव्य दस्तावेज़ खोलें

 स्रोत और गंतव्य दस्तावेज़ों को खोलें`Document` क्लास कन्स्ट्रक्टर. बदलें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: आयात प्रारूप विकल्प सेट करें

 इसका एक उदाहरण बनाएं`ImportFormatOptions` वर्ग और सेट`IgnoreHeaderFooter`संपत्ति को`false`यह सुनिश्चित करता है कि शीर्षलेख और पादलेख सामग्री को जोड़ने की प्रक्रिया के दौरान शामिल किया गया है।

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 उपयोग`AppendDocument` स्रोत दस्तावेज़ को जोड़ने के लिए गंतव्य दस्तावेज़ की विधि।`ImportFormatMode.KeepSourceFormatting`दूसरे पैरामीटर के रूप में और तीसरे पैरामीटर के रूप में आयात प्रारूप विकल्प।

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## चरण 5: गंतव्य दस्तावेज़ सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करते हुए शीर्षलेख और पादलेख सामग्री को अनदेखा करते हुए दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके हेडर फ़ुटर को अनदेखा करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```