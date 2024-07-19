---
title: पहलू अनुपात लॉक किया गया
linktitle: पहलू अनुपात लॉक किया गया
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में किसी आकृति के पहलू अनुपात को लॉक या अनलॉक करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/aspect-ratio-locked/
---

यह ट्यूटोरियल बताता है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में किसी आकृति के पहलू अनुपात को कैसे लॉक या अनलॉक किया जाए। पहलू अनुपात को लॉक करके, आप आकार बदलते समय आकृति के मूल अनुपात को बनाए रख सकते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"`उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`DocumentBuilder` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक छवि आकार डालें
 उपयोग`InsertImage` की विधि`DocumentBuilder`दस्तावेज़ में छवि आकार सम्मिलित करने के लिए ऑब्जेक्ट। पैरामीटर के रूप में छवि फ़ाइल का पथ प्रदान करें।

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## चरण 4: आस्पेक्ट रेशियो को लॉक या अनलॉक करें
 ठीक`AspectRatioLocked` आकृति का गुणधर्म`true` या`false` क्रमशः पहलू अनुपात को लॉक या अनलॉक करने के लिए।

```csharp
shape.AspectRatioLocked = false; // पहलू अनुपात अनलॉक करें
```

## चरण 5: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.AspectRatioLocked.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके आस्पेक्ट रेशियो लॉक्ड के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में किसी आकृति के पहलू अनुपात को सफलतापूर्वक लॉक या अनलॉक कर दिया है।