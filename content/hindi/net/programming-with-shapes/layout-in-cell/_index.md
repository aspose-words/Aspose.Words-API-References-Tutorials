---
title: सेल में लेआउट
linktitle: सेल में लेआउट
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका सेल के भीतर एक आकृति को लेआउट करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/layout-in-cell/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में तालिका सेल के भीतर एक आकृति को कैसे लेआउट किया जाए। आकृति गुणों को समायोजित करके और लेआउट विकल्पों का उपयोग करके, आप सेल के भीतर आकृति की स्थिति और उपस्थिति को नियंत्रित कर सकते हैं।

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

## चरण 3: तालिका बनाएं
 उपयोग`StartTable`, `EndTable`, `InsertCell` , और`Write` के तरीके`DocumentBuilder` तालिका बनाने के लिए ऑब्जेक्ट। का उपयोग करके वांछित पंक्ति ऊंचाई और ऊंचाई नियम सेट करें`RowFormat` गुण।

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## चरण 4: आकृति बनाएं और प्रारूपित करें
 एक बनाने के`Shape` वॉटरमार्क को परिभाषित करने के लिए ऑब्जेक्ट बनाएं और उसके गुणों को कॉन्फ़िगर करें। का उपयोग करके सेल के भीतर रखी जाने वाली आकृति को सेट करें`IsLayoutInCell` संपत्ति।

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## चरण 5: आकृति को अनुकूलित करें
 जैसे गुण सेट करके वॉटरमार्क आकार की उपस्थिति और पाठ को अनुकूलित करें`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, वगैरह।

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## चरण 6: दस्तावेज़ में आकृति डालें
का उपयोग करके दस्तावेज़ में वॉटरमार्क आकृति डालें`InsertNode` की विधि`DocumentBuilder` वस्तु। का उपयोग करके आकृति को स्थित करें`MoveTo` दस्तावेज़ में अंतिम बार चलाने के बाद इसे रखने की विधि।

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## चरण 7: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.LayoutInCell.docx" के रूप में सहेजते हैं।

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके लेआउट इन सेल के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // तालिका सेल के बाहर आकृति प्रदर्शित करें यदि इसे किसी सेल में रखा जाएगा।
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका सेल के भीतर सफलतापूर्वक एक आकृति तैयार कर ली है।