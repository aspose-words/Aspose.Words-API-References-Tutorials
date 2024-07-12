---
title: सेल में लेआउट
linktitle: सेल में लेआउट
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका कक्ष के भीतर आकृति का लेआउट बनाना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-shapes/layout-in-cell/
---

यह ट्यूटोरियल बताता है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में टेबल सेल के भीतर आकृति को कैसे लेआउट किया जाए। आकृति गुणों को समायोजित करके और लेआउट विकल्पों का उपयोग करके, आप सेल के भीतर आकृति की स्थिति और उपस्थिति को नियंत्रित कर सकते हैं।

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

## चरण 3: तालिका बनाएं
 उपयोग`StartTable`, `EndTable`, `InsertCell` , और`Write` के तरीके`DocumentBuilder`टेबल बनाने के लिए ऑब्जेक्ट का उपयोग करें। वांछित पंक्ति ऊंचाई और ऊंचाई नियम का उपयोग करके सेट करें`RowFormat` गुण।

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
 एक बनाने के`Shape` ऑब्जेक्ट और वॉटरमार्क को परिभाषित करने के लिए इसके गुणों को कॉन्फ़िगर करें। सेल के भीतर रखी जाने वाली आकृति को सेट करने के लिए वॉटरमार्क का उपयोग करें`IsLayoutInCell` संपत्ति।

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

## चरण 5: आकार को अनुकूलित करें
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
 दस्तावेज़ में वॉटरमार्क आकार डालें`InsertNode` की विधि`DocumentBuilder` ऑब्जेक्ट. आकृति को स्थिति में लाने के लिए इसका उपयोग करें`MoveTo` दस्तावेज़ में अंतिम रन के बाद इसे रखने की विधि।

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## चरण 7: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithShapes.LayoutInCell.docx" के रूप में सहेजते हैं।

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सेल में लेआउट के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
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
		IsLayoutInCell = true, // यदि आकृति को किसी सेल में रखा जाएगा तो उसे तालिका सेल के बाहर प्रदर्शित करें।
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

बस! आपने Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में तालिका सेल के भीतर सफलतापूर्वक एक आकृति बना ली है।