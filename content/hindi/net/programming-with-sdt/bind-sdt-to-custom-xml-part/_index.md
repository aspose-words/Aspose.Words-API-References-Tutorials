---
title: एसडीटी को कस्टम एक्सएमएल पार्ट से बांधें
linktitle: एसडीटी को कस्टम एक्सएमएल पार्ट से बांधें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके SDT को कस्टम Xml पार्ट से बाइंड करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

यह ट्यूटोरियल दर्शाता है कि .NET के लिए Aspose.Words का उपयोग करके एक स्ट्रक्चर्ड डॉक्यूमेंट टैग (SDT) को कस्टम Xml पार्ट से कैसे बांधा जाए। SDT आपको Word दस्तावेज़ में संरचित सामग्री नियंत्रण जोड़ने की अनुमति देता है, और CustomXmlParts दस्तावेज़ से जुड़े कस्टम XML डेटा को संग्रहीत करने का एक तरीका प्रदान करता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- सी# और एक्सएमएल का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और CustomXmlPart बनाएँ
 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`CustomXmlPart` कस्टम XML डेटा संग्रहीत करने के लिए. कस्टम XML मान्य XML प्रारूप में होना चाहिए. इस उदाहरण में, हम एक साधारण XML स्ट्रिंग का उपयोग करते हैं`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## चरण 3: दस्तावेज़ में एक स्ट्रक्चर्ड डॉक्यूमेंट टैग (एसडीटी) जोड़ें
 एक जोड़ना`StructuredDocumentTag` सामग्री नियंत्रण के रूप में कार्य करने के लिए दस्तावेज़ में। विवरण दें`SdtType` जैसा`PlainText` और यह`MarkupLevel` जैसा`Block` ब्लॉक-स्तरीय एसडीटी बनाने के लिए।

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## चरण 4: एसडीटी के लिए एक्सएमएल मैपिंग सेट करें
 एसडीटी को मैप करें`CustomXmlPart` का उपयोग करके`SetMapping` की विधि`XmlMapping` संपत्ति। विवरण दें`CustomXmlPart` , वांछित XML नोड का पता लगाने के लिए XPath अभिव्यक्ति, और यदि आवश्यक हो तो नेमस्पेस उपसर्ग। इस उदाहरण में, हम SDT को मैप करते हैं`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## चरण 5: दस्तावेज़ सहेजें
 का उपयोग करके संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.BindSDTtoCustomXmlPart.doc" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके बाइंड एसडी टीटीओ कस्टम एक्सएमएल पार्ट के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में एक SDT को CustomXmlPart से सफलतापूर्वक बांध दिया है।