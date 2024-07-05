---
title: मल्टी सेक्शन
linktitle: मल्टी सेक्शन
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में बहु-अनुभाग संरचित दस्तावेज़ टैग को पुनर्प्राप्त और संसाधित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/multi-section/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में मल्टी-सेक्शन संरचित दस्तावेज़ टैग के साथ कैसे काम किया जाए। आप दस्तावेज़ में मौजूद सेक्शन टैग को पुनः प्राप्त और संसाधित कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके आरंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और बहु-अनुभाग टैग पुनर्प्राप्त करें
 Word दस्तावेज़ को लोड करने के लिए निम्न का उपयोग करें:`Document` कंस्ट्रक्टर, दस्तावेज़ के पथ को पैरामीटर के रूप में पास करता है। दस्तावेज़ में सभी संरचित दस्तावेज़ टैग रेंज प्रारंभ नोड्स को पुनर्प्राप्त करने के लिए इसका उपयोग करें`GetChildNodes` तरीका।

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## चरण 3: मल्टी-सेक्शन टैग की प्रक्रिया करें
संरचित दस्तावेज़ टैग श्रेणी प्रारंभ नोड्स के संग्रह के माध्यम से पुनरावृति करें। इस उदाहरण में, हम बस प्रत्येक टैग का शीर्षक कंसोल पर प्रिंट करते हैं। आप अपनी आवश्यकताओं के आधार पर आगे की प्रक्रिया कर सकते हैं।

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### .NET के लिए Aspose.Words का उपयोग करके मल्टी सेक्शन के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में बहु-अनुभाग संरचित दस्तावेज़ टैग को सफलतापूर्वक पुनर्प्राप्त और संसाधित किया है।