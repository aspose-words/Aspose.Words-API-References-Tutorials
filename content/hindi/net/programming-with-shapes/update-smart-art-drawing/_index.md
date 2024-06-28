---
title: स्मार्ट आर्ट ड्राइंग को अपडेट करें
linktitle: स्मार्ट आर्ट ड्राइंग को अपडेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में स्मार्ट आर्ट ड्राइंग को अपडेट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/update-smart-art-drawing/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में स्मार्ट आर्ट ड्राइंग को कैसे अपडेट किया जाए। दस्तावेज़ में आकृतियों को दोहराकर और यह जांच कर कि क्या उनमें स्मार्ट आर्ट है, आप स्मार्ट आर्ट ड्राइंग को उसके डेटा में किए गए किसी भी बदलाव को प्रतिबिंबित करने के लिए अपडेट कर सकते हैं।

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
 का उपयोग करके उस वर्ड दस्तावेज़ को लोड करें जिसमें स्मार्ट आर्ट ड्राइंग शामिल है`Document` क्लास कंस्ट्रक्टर.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## चरण 3: स्मार्ट आर्ट ड्राइंग को अपडेट करें
 का उपयोग करके दस्तावेज़ में आकृतियों को दोहराएँ`GetChildNodes` विधि के साथ`NodeType.Shape` पैरामीटर. का उपयोग करके जांचें कि क्या प्रत्येक आकृति में स्मार्ट आर्ट है`HasSmartArt` संपत्ति, और यदि सत्य है, तो कॉल करें`UpdateSmartArtDrawing` स्मार्ट आर्ट ड्राइंग को अद्यतन करने की विधि।

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### .NET के लिए Aspose.Words का उपयोग करके स्मार्ट आर्ट ड्राइंग को अपडेट करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने वर्ड दस्तावेज़ में स्मार्ट आर्ट ड्राइंग को सफलतापूर्वक अपडेट किया है।