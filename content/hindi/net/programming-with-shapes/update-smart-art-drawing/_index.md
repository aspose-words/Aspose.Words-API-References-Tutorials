---
title: स्मार्ट आर्ट ड्राइंग अपडेट करें
linktitle: स्मार्ट आर्ट ड्राइंग अपडेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में स्मार्ट आर्ट ड्राइंग को अपडेट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/update-smart-art-drawing/
---

यह ट्यूटोरियल बताता है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में स्मार्ट आर्ट ड्राइंग को कैसे अपडेट किया जाए। दस्तावेज़ में आकृतियों के माध्यम से पुनरावृत्ति करके और जाँच करके कि क्या उनमें स्मार्ट आर्ट है, आप अपने डेटा में किए गए किसी भी परिवर्तन को दर्शाने के लिए स्मार्ट आर्ट ड्राइंग को अपडेट कर सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहां आपका दस्तावेज़ स्थित है।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करें
 स्मार्ट आर्ट ड्राइंग वाले वर्ड दस्तावेज़ को लोड करें`Document` क्लास निर्माता.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## चरण 3: स्मार्ट आर्ट ड्राइंग को अपडेट करें
 दस्तावेज़ में आकृतियों के माध्यम से पुनरावृत्ति करें`GetChildNodes` विधि के साथ`NodeType.Shape` पैरामीटर। जाँचें कि क्या प्रत्येक आकृति में स्मार्ट आर्ट है या नहीं`HasSmartArt` संपत्ति, और यदि सच है, तो कॉल करें`UpdateSmartArtDrawing` स्मार्ट आर्ट ड्राइंग को अपडेट करने की विधि।

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### .NET के लिए Aspose.Words का उपयोग करके स्मार्ट आर्ट ड्राइंग को अपडेट करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में स्मार्ट आर्ट ड्राइंग को सफलतापूर्वक अपडेट कर लिया है।