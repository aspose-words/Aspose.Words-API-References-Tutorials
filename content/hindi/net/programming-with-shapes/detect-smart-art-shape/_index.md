---
title: स्मार्ट आर्ट आकार का पता लगाएं
linktitle: स्मार्ट आर्ट आकार का पता लगाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके ग्राफ़िकल अभ्यावेदन की पहचान करके किसी Word दस्तावेज़ में स्मार्ट आर्ट आकृतियों का पता लगाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/detect-smart-art-shape/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में स्मार्ट आर्ट आकृतियों का पता कैसे लगाया जाए। स्मार्ट आर्ट आकृतियाँ ग्राफिकल अभ्यावेदन हैं जिनका उपयोग जानकारी और विचारों को दृश्य रूप से प्रस्तुत करने के लिए किया जाता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें
 का उपयोग करके Word दस्तावेज़ लोड करें`Document` कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है।

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## चरण 3: स्मार्ट कला आकृतियों का पता लगाएं
 प्रकार के चाइल्ड नोड्स के माध्यम से पुनरावृति करें`Shape` दस्तावेज़ में का उपयोग कर`GetChildNodes`तरीका। का उपयोग करके जांचें कि क्या प्रत्येक आकृति में स्मार्ट आर्ट है`HasSmart Art` संपत्ति।

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## चरण 4: परिणाम आउटपुट करें
दस्तावेज़ में पाई गई स्मार्ट आर्ट वाली आकृतियों की संख्या प्रिंट करें।

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### .NET के लिए Aspose.Words का उपयोग करके स्मार्ट आर्ट शेप का पता लगाने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में स्मार्ट आर्ट आकृतियों का सफलतापूर्वक पता लगा लिया है।