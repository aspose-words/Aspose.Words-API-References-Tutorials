---
title: सोर्स नंबरिंग रखें
linktitle: सोर्स नंबरिंग रखें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words में सोर्स नंबरिंग फ़ॉर्मेटिंग को संरक्षित करते हुए दस्तावेज़ को कैसे जोड़ा जाए।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/keep-source-numbering/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके क्रमांकित अनुच्छेदों के मूल क्रमांकन स्वरूपण को संरक्षित करते हुए किसी स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

-  .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहां स्रोत और गंतव्य दस्तावेज़ सहेजे जाएंगे।

## चरण 2: गंतव्य और स्रोत दस्तावेज़ बनाएं

 के उदाहरण बनाएँ`Document` गंतव्य और स्रोत दस्तावेज़ों के लिए।

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: आयात करते समय स्रोत क्रमांकन रखें

 स्रोत दस्तावेज़ से क्रमांकित अनुच्छेदों के क्रमांकन स्वरूपण को संरक्षित करने के लिए, इसका एक उदाहरण बनाएं`ImportFormatOptions` और सेट करें`KeepSourceNumbering` को`true` . का उपयोग करो`NodeImporter` निर्दिष्ट करते हुए, स्रोत दस्तावेज़ से गंतव्य दस्तावेज़ में नोड्स आयात करना`ImportFormatMode.KeepSourceFormatting` और यह`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## चरण 4: पैराग्राफ आयात करें और जोड़ें

स्रोत दस्तावेज़ में पैराग्राफ के माध्यम से पुनरावृत्ति करें और प्रत्येक पैराग्राफ को गंतव्य दस्तावेज़ में आयात करें`importer`. आयातित नोड्स को गंतव्य दस्तावेज़ के मुख्य भाग में जोड़ें।

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## चरण 5: संशोधित दस्तावेज़ सहेजें

 का उपयोग करके संशोधित दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके मूल क्रमांकन स्वरूपण को बनाए रखते हुए एक स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके सोर्स नंबरिंग बनाए रखने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// क्रमांकित पैराग्राफ आयात करते समय स्रोत सूची स्वरूपण रखें।
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```