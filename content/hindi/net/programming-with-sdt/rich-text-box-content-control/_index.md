---
title: रिच टेक्स्ट बॉक्स सामग्री नियंत्रण
linktitle: रिच टेक्स्ट बॉक्स सामग्री नियंत्रण
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में रिच टेक्स्ट बॉक्स सामग्री नियंत्रण कैसे बनाएं, जिससे टेक्स्ट फ़ॉर्मेटिंग और स्टाइलिंग सक्षम हो।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/rich-text-box-content-control/
---

यह ट्यूटोरियल प्रदर्शित करता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में रिच टेक्स्ट बॉक्स कंटेंट कंट्रोल कैसे बनाया जाता है। रिच टेक्स्ट बॉक्स कंटेंट कंट्रोल उपयोगकर्ताओं को विभिन्न शैलियों और फ़ॉर्मेटिंग विकल्पों के साथ टेक्स्ट दर्ज करने और फ़ॉर्मेट करने की अनुमति देता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और संरचित दस्तावेज़ टैग बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`StructuredDocumentTag` रिच टेक्स्ट बॉक्स सामग्री नियंत्रण का प्रतिनिधित्व करने के लिए। निर्दिष्ट करें`SdtType.RichText` प्रकार और`MarkupLevel.Block` ब्लॉक-स्तरीय रिच टेक्स्ट बॉक्स बनाने के लिए मार्कअप स्तर के रूप में।

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## चरण 3: रिच टेक्स्ट सामग्री बनाएं और प्रारूपित करें
एक पैराग्राफ़ बनाएँ और रिच टेक्स्ट कंटेंट को दर्शाने के लिए चलाएँ। टेक्स्ट और फ़ॉर्मेटिंग विकल्प जैसे रंग, फ़ॉन्ट, आदि सेट करें।

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## चरण 4: कंटेंट कंट्रोल में रिच टेक्स्ट कंटेंट जोड़ें
 पैराग्राफ को समृद्ध पाठ सामग्री के साथ जोड़ें`ChildNodes` रिच टेक्स्ट बॉक्स सामग्री नियंत्रण का संग्रह.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## चरण 5: दस्तावेज़ में सामग्री नियंत्रण जोड़ें
 दस्तावेज़ के मुख्य भाग में रिच टेक्स्ट बॉक्स सामग्री नियंत्रण को जोड़ने के लिए निम्न का उपयोग करें:`AppendChild` दस्तावेज़ के प्रथम भाग के मुख्य भाग की विधि।

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## चरण 6: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.RichTextBoxContentControl.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके रिच टेक्स्ट बॉक्स सामग्री नियंत्रण के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
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

बस! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में सफलतापूर्वक एक रिच टेक्स्ट बॉक्स सामग्री नियंत्रण बनाया है।