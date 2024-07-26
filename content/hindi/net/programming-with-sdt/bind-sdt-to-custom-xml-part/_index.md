---
title: SDT को कस्टम XML भाग से बाँधें
linktitle: SDT को कस्टम XML भाग से बाँधें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके SDT को कस्टम Xml पार्ट से बांधना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

यह ट्यूटोरियल प्रदर्शित करता है कि .NET के लिए Aspose.Words का उपयोग करके कस्टम XML पार्ट में स्ट्रक्चर्ड डॉक्यूमेंट टैग (SDT) को कैसे बांधा जाए। SDTs आपको Word डॉक्यूमेंट में स्ट्रक्चर्ड कंटेंट कंट्रोल जोड़ने की अनुमति देते हैं, और CustomXmlParts डॉक्यूमेंट से जुड़े कस्टम XML डेटा को स्टोर करने का एक तरीका प्रदान करते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और XML का बुनियादी ज्ञान.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके आरंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक दस्तावेज़ और CustomXmlPart बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`CustomXmlPart` कस्टम XML डेटा को संग्रहीत करने के लिए। कस्टम XML वैध XML प्रारूप में होना चाहिए। इस उदाहरण में, हम एक सरल XML स्ट्रिंग का उपयोग करते हैं`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## चरण 3: दस्तावेज़ में एक संरचित दस्तावेज़ टैग (SDT) जोड़ें
 एक जोड़ना`StructuredDocumentTag`दस्तावेज़ में सामग्री नियंत्रण के रूप में कार्य करने के लिए। निर्दिष्ट करें`SdtType` जैसा`PlainText` और यह`MarkupLevel` जैसा`Block` ब्लॉक-स्तरीय SDT बनाने के लिए.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## चरण 4: SDT के लिए XML मैपिंग सेट करें
 एसडीटी को मैप करें`CustomXmlPart` का उपयोग करके`SetMapping` की विधि`XmlMapping` संपत्ति निर्दिष्ट करें।`CustomXmlPart` , वांछित XML नोड का पता लगाने के लिए XPath अभिव्यक्ति, और यदि आवश्यक हो तो नामस्थान उपसर्ग। इस उदाहरण में, हम SDT को मैप करते हैं`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## चरण 5: दस्तावेज़ सहेजें
 संशोधित दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithSdt.BindSDTtoCustomXmlPart.doc" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके Bind Sd Tto Custom Xml Part के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में एक CustomXmlPart से SDT को सफलतापूर्वक जोड़ दिया है।