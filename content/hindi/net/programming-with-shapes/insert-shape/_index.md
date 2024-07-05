---
title: आकृति डालें
linktitle: आकृति डालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में आकृतियाँ सम्मिलित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/insert-shape/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में आकृतियाँ कैसे डालें। आकृतियों का उपयोग आपके दस्तावेज़ों के दृश्य स्वरूप और लेआउट को बढ़ाने के लिए किया जा सकता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 एक नया उदाहरण बनाएँ`Document` कक्षा और एक`DocumentBuilder`दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: आकृतियाँ सम्मिलित करें
 उपयोग`InsertShape` की विधि`DocumentBuilder`दस्तावेज़ में आकृतियाँ डालने के लिए ऑब्जेक्ट। आकृति का प्रकार, सापेक्ष क्षैतिज और ऊर्ध्वाधर स्थितियाँ, पृष्ठ आयाम, आकार और रैपिंग प्रकार निर्दिष्ट करें। आप चाहें तो आकृतियों का रोटेशन कोण भी सेट कर सकते हैं।

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.InsertShape.docx" के रूप में सहेजते हैं।

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### .NET के लिए Aspose.Words का उपयोग करके Insert Shape के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में सफलतापूर्वक आकृतियाँ सम्मिलित कर ली हैं।