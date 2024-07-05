---
title: आयात प्रारूप विकल्पों के साथ जोड़ें
linktitle: आयात प्रारूप विकल्पों के साथ जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके आयात प्रारूप विकल्पों के साथ दस्तावेज़ को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/append-with-import-format-options/
---

यह ट्यूटोरियल बताता है कि आयात प्रारूप विकल्पों के साथ एक दस्तावेज़ की सामग्री को दूसरे में जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि स्रोत और गंतव्य दस्तावेज़ों को कैसे खोलें, आयात प्रारूप विकल्प निर्दिष्ट करें, और स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में कैसे जोड़ें।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- दस्तावेज़ निर्देशिका पथ जहाँ स्रोत और गंतव्य दस्तावेज़ स्थित हैं।

## चरण 2: स्रोत और गंतव्य दस्तावेज़ खोलें

 स्रोत और गंतव्य दस्तावेज़ों को खोलें`Document` क्लास कन्स्ट्रक्टर. बदलें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## चरण 3: आयात प्रारूप विकल्प निर्दिष्ट करें

 इसका एक उदाहरण बनाएं`ImportFormatOptions` आयात प्रारूप विकल्प निर्दिष्ट करने के लिए क्लास। इस उदाहरण में, हम उपयोग करते हैं`KeepSourceNumbering` यह सुनिश्चित करने के लिए कि गंतव्य दस्तावेज़ के साथ टकराव होने पर स्रोत दस्तावेज़ से नंबरिंग का उपयोग किया जाता है, संपत्ति का उपयोग किया जाता है।

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## चरण 4: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 उपयोग`AppendDocument` स्रोत दस्तावेज़ को जोड़ने के लिए गंतव्य दस्तावेज़ की विधि।`ImportFormatMode.UseDestinationStyles` गंतव्य दस्तावेज़ की शैलियों और स्वरूपण का उपयोग करने के लिए दूसरे पैरामीटर के रूप में।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## चरण 5: गंतव्य दस्तावेज़ सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

इससे .NET के लिए Aspose.Words का उपयोग करके आयात प्रारूप विकल्पों के साथ दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा हो जाता है।

### .NET के लिए Aspose.Words का उपयोग करके आयात प्रारूप विकल्पों के साथ जोड़ें के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// निर्दिष्ट करें कि यदि स्रोत और गंतव्य दस्तावेज़ों में क्रमांकन में टकराव होता है,
	// तो स्रोत दस्तावेज़ से क्रमांकन का उपयोग किया जाएगा।
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```