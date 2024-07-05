---
title: कटे हुए कोने जोड़ें
linktitle: कटे हुए कोने जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: जानें कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में कोनों को काटकर आकृति कैसे जोड़ें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/add-corners-snipped/
---

 यह ट्यूटोरियल बताता है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में कोनों को काटकर आकार कैसे जोड़ा जाए। कोनों को काटकर आकार को अनुकूलित किया जा सकता है और इसका उपयोग करके डाला जा सकता है`InsertShape` तरीका।

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

## चरण 3: कोनों को काटकर आकार डालें
 उपयोग`InsertShape` की विधि`DocumentBuilder` कोनों को काटकर आकृति डालने के लिए ऑब्जेक्ट। आकृति का प्रकार निर्दिष्ट करें (इस मामले में,`ShapeType.TopCornersSnipped`) और आकृति के लिए वांछित आकार प्रदान करें.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## चरण 4: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.AddCornersSnipped.docx" के रूप में सहेजते हैं।

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### .NET के लिए Aspose.Words का उपयोग करके कोनों को जोड़ने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

बस! आपने Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ में कोनों से कटा हुआ आकार सफलतापूर्वक जोड़ लिया है।