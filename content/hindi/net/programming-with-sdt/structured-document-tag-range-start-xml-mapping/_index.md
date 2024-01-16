---
title: संरचित दस्तावेज़ टैग रेंज एक्सएमएल मैपिंग प्रारंभ करें
linktitle: संरचित दस्तावेज़ टैग रेंज एक्सएमएल मैपिंग प्रारंभ करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में संरचित दस्तावेज़ टैग रेंज प्रारंभ के लिए XML मैपिंग कैसे सेट करें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में संरचित दस्तावेज़ टैग रेंज प्रारंभ के लिए XML मैपिंग कैसे सेट करें। XML मैपिंग आपको सामग्री नियंत्रण के भीतर XML डेटा स्रोत के विशिष्ट भागों को प्रदर्शित करने की अनुमति देती है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और XML भाग बनाएँ
 का उपयोग करके Word दस्तावेज़ लोड करें`Document` कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है। एक XML भाग बनाएं जिसमें वह डेटा हो जिसे आप संरचित दस्तावेज़ टैग के भीतर प्रदर्शित करना चाहते हैं।

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## चरण 3: संरचित दस्तावेज़ टैग के लिए XML मैपिंग सेट करें
दस्तावेज़ से संरचित दस्तावेज़ टैग श्रेणी प्रारंभ को पुनः प्राप्त करें। फिर, XPath अभिव्यक्ति का उपयोग करके कस्टम XML भाग के एक विशिष्ट भाग को प्रदर्शित करने के लिए संरचित दस्तावेज़ टैग के लिए XML मैपिंग सेट करें।

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## चरण 4: दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके संरचित दस्तावेज़ टैग रेंज स्टार्ट Xml मैपिंग के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// एक XML भाग का निर्माण करें जिसमें डेटा हो और इसे दस्तावेज़ के CustomXmlPart संग्रह में जोड़ें।
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// एक StructuredDocumentTag बनाएं जो दस्तावेज़ में हमारे CustomXmlPart की सामग्री प्रदर्शित करेगा।
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// यदि हम अपने StructuredDocumentTag के लिए मैपिंग सेट करते हैं,
	// यह केवल CustomXmlPart का वह भाग प्रदर्शित करेगा जिसकी ओर XPath इंगित करता है।
	// यह XPath हमारे CustomXmlPart के पहले "<root>" तत्व के दूसरे "<text>" तत्व की सामग्री को इंगित करेगा।
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में एक संरचित दस्तावेज़ टैग रेंज प्रारंभ के लिए XML मैपिंग सफलतापूर्वक सेट कर ली है।