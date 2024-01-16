---
title: रिच टेक्स्ट बॉक्स सामग्री नियंत्रण
linktitle: रिच टेक्स्ट बॉक्स सामग्री नियंत्रण
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: टेक्स्ट फ़ॉर्मेटिंग और स्टाइल को सक्षम करने वाले .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में रिच टेक्स्ट बॉक्स सामग्री नियंत्रण बनाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/rich-text-box-content-control/
---

यह ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में रिच टेक्स्ट बॉक्स सामग्री नियंत्रण कैसे बनाया जाए। रिच टेक्स्ट बॉक्स सामग्री नियंत्रण उपयोगकर्ताओं को विभिन्न शैलियों और स्वरूपण विकल्पों के साथ पाठ दर्ज करने और प्रारूपित करने की अनुमति देता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और संरचित दस्तावेज़ टैग बनाएं
 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`StructuredDocumentTag` रिच टेक्स्ट बॉक्स सामग्री नियंत्रण का प्रतिनिधित्व करने के लिए। उल्लिखित करना`SdtType.RichText` प्रकार और के रूप में`MarkupLevel.Block` ब्लॉक-स्तरीय रिच टेक्स्ट बॉक्स बनाने के लिए मार्कअप स्तर के रूप में।

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## चरण 3: रिच टेक्स्ट सामग्री बनाएं और प्रारूपित करें
एक पैराग्राफ बनाएं और समृद्ध पाठ सामग्री का प्रतिनिधित्व करने के लिए चलाएं। टेक्स्ट और फ़ॉर्मेटिंग विकल्प जैसे रंग, फ़ॉन्ट इत्यादि सेट करें।

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## चरण 4: रिच टेक्स्ट सामग्री को सामग्री नियंत्रण में जोड़ें
इसमें समृद्ध पाठ्य सामग्री वाला पैराग्राफ जोड़ें`ChildNodes` रिच टेक्स्ट बॉक्स सामग्री नियंत्रण का संग्रह।

```csharp
sdtRichText.ChildNodes.Add(para);
```

## चरण 5: दस्तावेज़ में सामग्री नियंत्रण जोड़ें
 का उपयोग करके रिच टेक्स्ट बॉक्स सामग्री नियंत्रण को दस्तावेज़ के मुख्य भाग में जोड़ें`AppendChild` दस्तावेज़ के पहले खंड के मुख्य भाग की विधि।

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## चरण 6: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.RichTextBoxContentControl.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके रिच टेक्स्ट बॉक्स सामग्री नियंत्रण के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में सफलतापूर्वक एक रिच टेक्स्ट बॉक्स सामग्री नियंत्रण बनाया है।