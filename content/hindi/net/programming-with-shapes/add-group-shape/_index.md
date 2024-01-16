---
title: समूह आकार जोड़ें
linktitle: समूह आकार जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में एकाधिक आकृतियों के साथ समूह आकृति जोड़ने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/add-group-shape/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में एकाधिक आकृतियों वाले समूह आकार को कैसे जोड़ा जाए। समूह आकार आपको एक ही इकाई के रूप में कई आकृतियों को संयोजित और हेरफेर करने की अनुमति देते हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, आपके पास निम्नलिखित होना चाहिए:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित।
- वर्ड दस्तावेजों के साथ सी# और वर्ड प्रोसेसिंग का बुनियादी ज्ञान।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
 अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके प्रारंभ करें। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उस निर्देशिका के वास्तविक पथ के साथ जहां आप दस्तावेज़ को सहेजना चाहते हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और ग्रुपशेप बनाएं
 का एक नया उदाहरण बनाएं`Document` कक्षा और`GroupShape` दस्तावेज़ के साथ काम करने पर आपत्ति।

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## चरण 3: ग्रुपशेप में आकृतियाँ बनाएँ और जोड़ें
 जैसे अलग-अलग आकृतियाँ बनाएँ`accentBorderShape` और`actionButtonShape` का उपयोग`Shape` कक्षा। उनके गुणों को इच्छानुसार अनुकूलित करें। इन आकृतियों को इसमें जोड़ें`groupShape` वस्तु।

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
 के लिए चौड़ाई, ऊंचाई और समन्वय आकार निर्धारित करें`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## चरण 5: दस्तावेज़ में GroupShape डालें
 एक बनाने के`DocumentBuilder` ऑब्जेक्ट करें और डालें`groupShape` का उपयोग करके दस्तावेज़ में`InsertNode` तरीका।

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## चरण 6: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save`तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.AddGroupShape.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके समूह आकार जोड़ने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
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

इतना ही! आपने Aspose.W का उपयोग करके अपने Word दस्तावेज़ में एकाधिक आकृतियों वाला एक समूह आकार सफलतापूर्वक जोड़ा है