---
title: Word दस्तावेज़ में पैराग्राफ़ पर बॉर्डर और छायांकन लागू करें
linktitle: Word दस्तावेज़ में पैराग्राफ़ पर बॉर्डर और छायांकन लागू करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ वर्ड दस्तावेज़ में एक पैराग्राफ में बॉर्डर और शेडिंग कैसे लागू करें, सीखें।
type: docs
weight: 10
url: /hi/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
इस ट्यूटोरियल में, हम आपको दिखाने जा रहे हैं कि .NET के लिए Aspose.Words की कार्यक्षमता का उपयोग करके वर्ड दस्तावेज़ में एक पैराग्राफ में बॉर्डर और शेडिंग कैसे लागू करें। स्रोत कोड को समझने और फ़ॉर्मेटिंग परिवर्तन लागू करने के लिए नीचे दिए गए चरणों का पालन करें।

## चरण 1: दस्तावेज़ बनाना और कॉन्फ़िगर करना

आरंभ करने के लिए, एक नया दस्तावेज़ और एक संबद्ध DocumentBuilder ऑब्जेक्ट बनाएं। ऐसे:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 2: सीमा विन्यास

अब प्रत्येक पक्ष के लिए सीमा शैली निर्दिष्ट करके पैराग्राफ सीमाओं को कॉन्फ़िगर करें। ऐसे:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## चरण 3: इन्फिल सेटअप

अब हम बनावट और भरण रंगों को निर्दिष्ट करके पैराग्राफ भरण को कॉन्फ़िगर करेंगे। ऐसे:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## चरण 4: सामग्री जोड़ें

हम पैराग्राफ में कुछ स्वरूपित सामग्री जोड़ने जा रहे हैं। ऐसे:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## चरण 3: दस्तावेज़ सहेजना

 टेक्स्ट इनपुट फॉर्म फ़ील्ड डालने के बाद, दस्तावेज़ को वांछित स्थान पर सहेजें`Save` तरीका। उचित फ़ाइल पथ प्रदान करना सुनिश्चित करें:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### .NET के लिए Aspose.Words का उपयोग करके पैराग्राफ में बॉर्डर और शेडिंग लागू करने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words के साथ बॉर्डर लागू करें और पैराग्राफ़ में शेडिंग सुविधा के लिए संपूर्ण स्रोत कोड यहां दिया गया है:

```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में पैराग्राफ पर बॉर्डर और शेडिंग कैसे लागू करें। पैराग्राफ को कॉन्फ़िगर करके`Borders` और`Shading` गुण, हम पैराग्राफ के लिए सीमा शैली, रेखा रंग और रंग भरने में सक्षम थे। .NET के लिए Aspose.Words पैराग्राफों की उपस्थिति को अनुकूलित करने और आपके दस्तावेज़ों के दृश्य प्रतिनिधित्व को बढ़ाने के लिए शक्तिशाली स्वरूपण क्षमताएं प्रदान करता है।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में पैराग्राफ पर बॉर्डर और शेडिंग कैसे लागू करूं?

उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में पैराग्राफ पर बॉर्डर और शेडिंग लागू करने के लिए, इन चरणों का पालन करें:
1.  एक नया दस्तावेज़ बनाएं और a`DocumentBuilder` वस्तु।
2.  तक पहुंच कर पैराग्राफ सीमाओं को कॉन्फ़िगर करें`Borders` की संपत्ति`ParagraphFormat` और प्रत्येक पक्ष के लिए सीमा शैली निर्धारित करना।
3.  तक पहुंच कर पैराग्राफ़ भरण को कॉन्फ़िगर करें`Shading` की संपत्ति`ParagraphFormat` और बनावट निर्दिष्ट करना और रंग भरना।
4.  का उपयोग करके अनुच्छेद में सामग्री जोड़ें`Write` की विधि`DocumentBuilder`.
5.  का उपयोग करके दस्तावेज़ को सहेजें`Save` तरीका।

#### प्रश्न: मैं अनुच्छेद के प्रत्येक पक्ष के लिए सीमा शैली कैसे निर्धारित करूं?

 उ: पैराग्राफ के प्रत्येक पक्ष के लिए बॉर्डर शैली सेट करने के लिए, आप इसका उपयोग कर सकते हैं`Borders` की संपत्ति`ParagraphFormat` और सेट करें`LineStyle` प्रत्येक के लिए संपत्ति`BorderType` (जैसे,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). आप विभिन्न पंक्ति शैलियों को निर्दिष्ट कर सकते हैं जैसे कि`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, वगैरह।

#### प्रश्न: मैं पैराग्राफ शेडिंग के लिए बनावट कैसे निर्दिष्ट करूं और रंग कैसे भरूं?

 उ: पैराग्राफ शेडिंग के लिए बनावट निर्दिष्ट करने और रंग भरने के लिए, आप इसका उपयोग कर सकते हैं`Shading` की संपत्ति`ParagraphFormat` और सेट करें`Texture` वांछित बनावट सूचकांक की संपत्ति (उदाहरण के लिए,`TextureIndex.TextureDiagonalCross` ). आप भी सेट कर सकते हैं`BackgroundPatternColor` और`ForegroundPatternColor` का उपयोग करके वांछित रंगों के गुण`System.Drawing.Color` कक्षा।