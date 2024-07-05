---
title: समूह आकार जोड़ें
linktitle: समूह आकार जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एकाधिक आकृतियों के साथ समूह आकृति जोड़ने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/add-group-shape/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एकाधिक आकृतियों वाले समूह आकृति को कैसे जोड़ा जाए। समूह आकृतियाँ आपको एक इकाई के रूप में कई आकृतियों को संयोजित और हेरफेर करने की अनुमति देती हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपके पास निम्नलिखित चीजें होनी चाहिए:

- Aspose.Words for .NET लाइब्रेरी स्थापित की गई।
- C# और वर्ड दस्तावेजों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपने दस्तावेज़ निर्देशिका का पथ सेट करके प्रारंभ करें।`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका का वास्तविक पथ जहाँ आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और GroupShape बनाएँ
 एक नया उदाहरण बनाएँ`Document` वर्ग और`GroupShape`दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## चरण 3: ग्रुपशेप में आकृतियाँ बनाएँ और जोड़ें
 व्यक्तिगत आकृतियाँ बनाएँ जैसे कि`accentBorderShape` और`actionButtonShape` का उपयोग`Shape` वर्ग। अपनी इच्छानुसार उनके गुणों को अनुकूलित करें। इन आकृतियों को वर्ग में जोड़ें`groupShape` वस्तु।

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## चरण 4: ग्रुपशेप के लिए आयाम सेट करें
 के लिए चौड़ाई, ऊंचाई और निर्देशांक आकार सेट करें`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## चरण 5: दस्तावेज़ में ग्रुपशेप डालें
 एक बनाने के`DocumentBuilder` ऑब्जेक्ट और डालें`groupShape` दस्तावेज़ में का उपयोग कर`InsertNode` तरीका।

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## चरण 6: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.AddGroupShape.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके समूह आकार जोड़ने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

बस! आपने Aspose.W का उपयोग करके अपने Word दस्तावेज़ में कई आकृतियों वाला समूह आकार सफलतापूर्वक जोड़ लिया है