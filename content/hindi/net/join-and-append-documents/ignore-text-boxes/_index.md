---
title: टेक्स्ट बॉक्स को अनदेखा करें
linktitle: टेक्स्ट बॉक्स को अनदेखा करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके टेक्स्ट बॉक्स फ़ॉर्मेटिंग को अनदेखा करते हुए दस्तावेज़ को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/ignore-text-boxes/
---

यह ट्यूटोरियल बताता है कि टेक्स्ट बॉक्स के फ़ॉर्मेटिंग को संरक्षित करते हुए दस्तावेज़ को जोड़ने के लिए Aspose.Words for .NET का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड प्रदर्शित करता है कि जोड़ने की प्रक्रिया के दौरान टेक्स्ट बॉक्स को शामिल करने के लिए आयात प्रारूप विकल्पों को कैसे सेट किया जाए।

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

## चरण 3: आयात प्रारूप विकल्प सेट करें

 इसका एक उदाहरण बनाएं`ImportFormatOptions` वर्ग और सेट`IgnoreTextBoxes`संपत्ति को`false`यह सुनिश्चित करता है कि पाठ बॉक्स को उनके स्वरूपण को संरक्षित करते हुए जोड़ने की प्रक्रिया के दौरान शामिल किया जाए।

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## चरण 4: टेक्स्ट बॉक्स सामग्री जोड़ें

 एक बनाने के`NodeImporter`ऑब्जेक्ट का उपयोग करें और स्रोत दस्तावेज़ से गंतव्य दस्तावेज़ में टेक्स्ट बॉक्स नोड्स आयात करने के लिए इसका उपयोग करें। स्रोत दस्तावेज़ में प्रत्येक पैराग्राफ़ के माध्यम से पुनरावृति करें और इसे गंतव्य दस्तावेज़ में आयात करें।

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## चरण 5: गंतव्य दस्तावेज़ सहेजें

अंत में, संशोधित गंतव्य दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

इससे .NET के लिए Aspose.Words का उपयोग करते हुए टेक्स्ट बॉक्स स्वरूपण को संरक्षित करते हुए दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा हो जाता है।

### .NET के लिए Aspose.Words का उपयोग करके टेक्स्ट बॉक्स को अनदेखा करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// आयात करते समय स्रोत पाठ बॉक्स का स्वरूपण बनाए रखें.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```