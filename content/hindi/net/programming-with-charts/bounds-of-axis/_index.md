---
title: एक चार्ट में अक्ष की सीमा
linktitle: एक चार्ट में अक्ष की सीमा
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: जानें कि अक्ष पर प्रदर्शित मानों की सीमा को नियंत्रित करने के लिए .NET के लिए Aspose.Words का उपयोग करके चार्ट में अक्ष की सीमाएं कैसे सेट करें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/bounds-of-axis/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट में अक्ष की सीमा कैसे निर्धारित करें। एक चार्ट सम्मिलित करके, श्रृंखला डेटा जोड़कर, और अक्ष स्केलिंग को कॉन्फ़िगर करके, आप अक्ष के लिए न्यूनतम और अधिकतम मान परिभाषित कर सकते हैं।

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

## चरण 3: एक चार्ट सम्मिलित करें और कॉन्फ़िगर करें
 का उपयोग करके दस्तावेज़ में एक चार्ट डालें`InsertChart` की विधि`DocumentBuilder` वस्तु। वांछित चार्ट प्रकार और आयाम सेट करें।

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## चरण 4: श्रृंखला डेटा जोड़ें
चार्ट में किसी भी मौजूदा श्रृंखला को साफ़ करें और नई श्रृंखला डेटा जोड़ें। इस उदाहरण में, हम "आइटम 1" से "आइटम 5" लेबल और संबंधित मानों के साथ एक श्रृंखला जोड़ते हैं।

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## चरण 5: अक्ष की सीमाएँ निर्धारित करें
 का उपयोग करके न्यूनतम और अधिकतम मान सेट करके Y-अक्ष की स्केलिंग को कॉन्फ़िगर करें`Scaling.Minimum` और`Scaling.Maximum` अक्ष के गुण.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## चरण 6: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithCharts.BoundsOfAxis.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके बाउंड्स ऑफ़ एक्सिस के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

इतना ही! आपने .NET के लिए Aspose.Words का उपयोग करके चार्ट में एक अक्ष की सीमाएं सफलतापूर्वक निर्धारित कर ली हैं।

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट में एक अक्ष की सीमा कैसे निर्धारित करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक चार्ट सम्मिलित और कॉन्फ़िगर कर सकते हैं, श्रृंखला डेटा जोड़ सकते हैं, और अक्ष स्केलिंग के लिए न्यूनतम और अधिकतम मान परिभाषित कर सकते हैं। Aspose.Words for .NET, Word दस्तावेज़ों के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है, जिससे आप आसानी से गतिशील और देखने में आकर्षक चार्ट बना सकते हैं।


### पूछे जाने वाले प्रश्न

#### Q1. .NET के लिए Aspose.Words क्या है?
.NET के लिए Aspose.Words एक लाइब्रेरी है जो डेवलपर्स को Word दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। यह Word दस्तावेज़ों को बनाने, हेरफेर करने और सहेजने के लिए सुविधाओं और कार्यात्मकताओं की एक विस्तृत श्रृंखला प्रदान करता है।

#### Q2. मैं .NET के लिए Aspose.Words कैसे स्थापित कर सकता हूँ?
.NET के लिए Aspose.Words स्थापित करने के लिए, आप विजुअल स्टूडियो में NuGet पैकेज मैनेजर का उपयोग कर सकते हैं। बस NuGet पैकेज मैनेजर में "Aspose.Words" खोजें और इसे अपने प्रोजेक्ट में इंस्टॉल करें।

#### Q3. क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Words का उपयोग कर सकता हूँ?
नहीं, Aspose.Words for .NET विशेष रूप से .NET अनुप्रयोगों के लिए डिज़ाइन किया गया है। यह C# और VB.NET जैसी प्रोग्रामिंग भाषाओं के साथ काम करता है।

#### Q4. क्या .NET के लिए Aspose.Words का उपयोग करने के लिए कोई अन्य शर्तें हैं?
.NET लाइब्रेरी के लिए Aspose.Words इंस्टॉल करने के अलावा, आपको C# प्रोग्रामिंग और Word दस्तावेज़ों के साथ वर्ड प्रोसेसिंग का बुनियादी ज्ञान होना चाहिए। .NET ढांचे से परिचित होना भी सहायक होगा।
