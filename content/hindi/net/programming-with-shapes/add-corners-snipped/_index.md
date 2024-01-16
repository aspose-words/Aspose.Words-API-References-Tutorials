---
title: कटे हुए कोने जोड़ें
linktitle: कटे हुए कोने जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में काटे गए कोनों के साथ एक आकृति जोड़ने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/add-corners-snipped/
---

 यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में काटे गए कोनों के साथ एक आकृति कैसे जोड़ें। कोनों के कटे हुए आकार को अनुकूलित किया जा सकता है और इसका उपयोग करके डाला जा सकता है`InsertShape` तरीका।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़बिल्डर बनाएँ
 का एक नया उदाहरण बनाएं`Document` कक्षा और ए`DocumentBuilder` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: कोनों को कटा हुआ आकार डालें
 उपयोग`InsertShape` की विधि`DocumentBuilder` कोनों को काटकर एक आकृति सम्मिलित करने के लिए ऑब्जेक्ट। आकृति प्रकार निर्दिष्ट करें (इस मामले में,`ShapeType.TopCornersSnipped`) और आकृति के लिए वांछित आकार प्रदान करें।

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## चरण 4: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.AddCornersSnipped.docx" के रूप में सहेजते हैं।

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### .NET के लिए Aspose.Words का उपयोग करके ऐड कॉर्नर स्निप्ड के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
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

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ में कोनों से कटा हुआ आकार सफलतापूर्वक जोड़ लिया है।