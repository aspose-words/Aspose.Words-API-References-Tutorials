---
title: अलग पेज सेटअप
linktitle: अलग पेज सेटअप
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके विभिन्न पेज सेटअप सेटिंग्स के साथ दस्तावेज़ को जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/different-page-setup/
---

यह ट्यूटोरियल बताता है कि किसी दस्तावेज़ को विभिन्न पेज सेटअप सेटिंग्स के साथ किसी अन्य दस्तावेज़ में जोड़ने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि स्रोत और गंतव्य दस्तावेज़ों के लिए अलग-अलग पेज सेटिंग्स कैसे सेट करें और उचित निरंतरता और क्रमांकन सुनिश्चित करें।

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

## चरण 3: स्रोत दस्तावेज़ के लिए पृष्ठ सेटिंग सेट करें

 उचित निरंतरता और क्रमांकन सुनिश्चित करने के लिए स्रोत दस्तावेज़ की पृष्ठ सेटअप सेटिंग्स समायोजित करें। इस उदाहरण में, हमने अनुभाग को प्रारंभ पर सेट किया है`SectionStart.Continuous` और पृष्ठ क्रमांकन पुनः प्रारंभ करें. हम यह भी सुनिश्चित करते हैं कि पृष्ठ की चौड़ाई, ऊंचाई और अभिविन्यास गंतव्य दस्तावेज़ के अंतिम अनुभाग से मेल खाते हों।

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## चरण 4: अनुच्छेद स्वरूपण को संशोधित करें

 उचित स्वरूपण बनाए रखने के लिए, स्रोत दस्तावेज़ में सभी अनुच्छेदों को पुनरावृत्त करें और सेट करें`KeepWithNext`संपत्ति को`true`यह सुनिश्चित करता है कि जोड़ने की प्रक्रिया के दौरान पैराग्राफ एक साथ रहें।

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 उपयोग`AppendDocument` स्रोत स्वरूपण को संरक्षित करते हुए, संशोधित स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ने के लिए गंतव्य दस्तावेज़ की विधि।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## चरण 6: गंतव्य दस्तावेज़ सहेजें

 अंत में, संशोधित गंतव्य दस्तावेज़ का उपयोग करके सहेजें`Save` की विधि`Document` वस्तु।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके विभिन्न पेज सेटअप सेटिंग्स के साथ एक दस्तावेज़ को जोड़ने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके विभिन्न पेज सेटअप के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// गंतव्य दस्तावेज़ की समाप्ति के बाद सीधे जारी रखने के लिए स्रोत दस्तावेज़ को सेट करें।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// स्रोत दस्तावेज़ के आरंभ में पृष्ठ क्रमांकन पुनः आरंभ करें।
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// यह सुनिश्चित करने के लिए कि ऐसा तब न हो जब स्रोत दस्तावेज़ में अलग-अलग पेज सेटअप सेटिंग्स हों, सुनिश्चित करें
	// गंतव्य दस्तावेज़ के अंतिम अनुभाग के बीच सेटिंग्स समान हैं।
	// यदि स्रोत दस्तावेज़ में आगे निरंतर अनुभाग हैं,
	//इसे उन अनुभागों के लिए दोहराने की आवश्यकता होगी।
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// स्रोत दस्तावेज़ में सभी अनुभागों को दोहराएँ।
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```