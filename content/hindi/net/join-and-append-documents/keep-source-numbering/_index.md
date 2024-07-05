---
title: स्रोत क्रमांकन रखें
linktitle: स्रोत क्रमांकन रखें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words में स्रोत क्रमांकन स्वरूपण को संरक्षित करते हुए दस्तावेज़ को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/keep-source-numbering/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके क्रमांकित पैराग्राफों के मूल क्रमांकन स्वरूपण को संरक्षित करते हुए स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में कैसे जोड़ा जाए।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Releases]https://releases.aspose.com/words/net/ या इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करें।
- एक दस्तावेज़ निर्देशिका पथ जहाँ स्रोत और गंतव्य दस्तावेज़ सहेजे जाएंगे.

## चरण 2: गंतव्य और स्रोत दस्तावेज़ बनाएँ

 के उदाहरण बनाएं`Document` गंतव्य और स्रोत दस्तावेज़ों के लिए.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## चरण 3: आयात करते समय स्रोत क्रमांकन रखें

 स्रोत दस्तावेज़ से क्रमांकित पैराग्राफ़ों के क्रमांकन स्वरूपण को संरक्षित करने के लिए, इसका एक उदाहरण बनाएँ`ImportFormatOptions` और सेट करें`KeepSourceNumbering` को`true` । का उपयोग करो`NodeImporter` स्रोत दस्तावेज़ से गंतव्य दस्तावेज़ में नोड्स आयात करने के लिए, निर्दिष्ट करना`ImportFormatMode.KeepSourceFormatting` और यह`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## चरण 4: पैराग्राफ़ आयात करें और जोड़ें

 स्रोत दस्तावेज़ में पैराग्राफ़ों के माध्यम से पुनरावृत्ति करें और प्रत्येक पैराग्राफ़ को गंतव्य दस्तावेज़ में आयात करें`importer`आयातित नोड्स को गंतव्य दस्तावेज़ के मुख्य भाग में जोड़ें.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## चरण 5: संशोधित दस्तावेज़ को सहेजें

 संशोधित दस्तावेज़ को सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करते हुए मूल क्रमांकन स्वरूपण को बनाए रखते हुए एक स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ने के कार्यान्वयन को पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके स्रोत क्रमांकन बनाए रखने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//क्रमांकित पैराग्राफ़ आयात करते समय स्रोत सूची स्वरूपण बनाए रखें.
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