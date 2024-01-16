---
title: मल्टी सेक्शन
linktitle: मल्टी सेक्शन
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में मल्टी-सेक्शन संरचित दस्तावेज़ टैग को पुनर्प्राप्त और संसाधित करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-sdt/multi-section/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में मल्टी-सेक्शन संरचित दस्तावेज़ टैग के साथ कैसे काम किया जाए। आप दस्तावेज़ में मौजूद अनुभाग टैग को पुनः प्राप्त और संसाधित कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें और मल्टी-सेक्शन टैग पुनः प्राप्त करें
 का उपयोग करके Word दस्तावेज़ लोड करें`Document` कंस्ट्रक्टर, एक पैरामीटर के रूप में दस्तावेज़ का पथ पास कर रहा है। का उपयोग करके दस्तावेज़ में सभी संरचित दस्तावेज़ टैग रेंज प्रारंभ नोड्स को पुनः प्राप्त करें`GetChildNodes` तरीका।

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## चरण 3: मल्टी-सेक्शन टैग की प्रक्रिया करें
संरचित दस्तावेज़ टैग रेंज प्रारंभ नोड्स के संग्रह के माध्यम से पुनरावृति करें। इस उदाहरण में, हम बस प्रत्येक टैग का शीर्षक कंसोल पर प्रिंट करते हैं। आप अपनी आवश्यकताओं के आधार पर आगे की प्रक्रिया कर सकते हैं।

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### .NET के लिए Aspose.Words का उपयोग करके मल्टी सेक्शन के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में बहु-खंड संरचित दस्तावेज़ टैग को सफलतापूर्वक पुनर्प्राप्त और संसाधित किया है।