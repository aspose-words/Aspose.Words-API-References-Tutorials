---
title: विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क जोड़ें
linktitle: विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क जोड़ने का तरीका जानें। चरण-दर-चरण मार्गदर्शिका.
type: docs
weight: 10
url: /hi/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words का उपयोग करके विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क कैसे जोड़ा जाए। टेक्स्ट वॉटरमार्क किसी दस्तावेज़ पर यह दर्शाने के लिए लगाया गया टेक्स्ट है कि यह एक मसौदा, गोपनीय आदि है।

## चरण 1: दस्तावेज़ जनरेटर का उपयोग करना

सबसे पहले, हम अपने दस्तावेज़ में सामग्री जोड़ने के लिए एक दस्तावेज़ जनरेटर का उपयोग करेंगे।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: दस्तावेज़ लोड करना

हम दस्तावेज़ पथ का उपयोग करके मौजूदा दस्तावेज़ को लोड करेंगे।

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## चरण 3: विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क जोड़ें

 हम इसका एक उदाहरण बनाएंगे`TextWatermarkOptions` क्लास करें और टेक्स्ट वॉटरमार्क के लिए वांछित विकल्प सेट करें।

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## चरण 4: दस्तावेज़ सहेजें

अंत में, हम दस्तावेज़ को जोड़े गए टेक्स्ट वॉटरमार्क के साथ सहेज सकते हैं।

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### .NET के लिए Aspose.Words के साथ विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क जोड़ने के लिए उदाहरण स्रोत कोड

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.Words का उपयोग करके विशिष्ट विकल्पों के साथ टेक्स्ट वॉटरमार्क कैसे जोड़ा जाता है।

