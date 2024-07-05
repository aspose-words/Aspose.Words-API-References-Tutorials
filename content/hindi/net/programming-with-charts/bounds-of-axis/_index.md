---
title: चार्ट में अक्ष की सीमा
linktitle: चार्ट में अक्ष की सीमा
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: Aspose.Words for .NET का उपयोग करके चार्ट में अक्ष की सीमा निर्धारित करना सीखें, अक्ष पर प्रदर्शित मानों की सीमा को नियंत्रित करें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/bounds-of-axis/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट में अक्ष की सीमा कैसे निर्धारित करें। चार्ट सम्मिलित करके, श्रृंखला डेटा जोड़कर, और अक्ष स्केलिंग को कॉन्फ़िगर करके, आप अक्ष के लिए न्यूनतम और अधिकतम मान परिभाषित कर सकते हैं।

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

## चरण 3: चार्ट डालें और कॉन्फ़िगर करें
 दस्तावेज़ में चार्ट डालने के लिए निम्न का उपयोग करें:`InsertChart` की विधि`DocumentBuilder` ऑब्जेक्ट. इच्छित चार्ट प्रकार और आयाम सेट करें.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## चरण 4: श्रृंखला डेटा जोड़ें
चार्ट में किसी भी मौजूदा श्रृंखला को साफ़ करें और नई श्रृंखला डेटा जोड़ें। इस उदाहरण में, हम "आइटम 1" से "आइटम 5" लेबल और संबंधित मानों वाली श्रृंखला जोड़ते हैं।

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## चरण 5: अक्ष की सीमा निर्धारित करें
 का उपयोग करके न्यूनतम और अधिकतम मान सेट करके Y-अक्ष की स्केलिंग कॉन्फ़िगर करें`Scaling.Minimum` और`Scaling.Maximum` अक्ष के गुण.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## चरण 6: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithCharts.BoundsOfAxis.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके Bounds Of Axis के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
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

बस! आपने .NET के लिए Aspose.Words का उपयोग करके चार्ट में अक्ष की सीमा सफलतापूर्वक सेट कर ली है।

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Words for .NET का उपयोग करके चार्ट में अक्ष की सीमा कैसे निर्धारित करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप चार्ट सम्मिलित और कॉन्फ़िगर कर सकते हैं, श्रृंखला डेटा जोड़ सकते हैं, और अक्ष स्केलिंग के लिए न्यूनतम और अधिकतम मान परिभाषित कर सकते हैं। Aspose.Words for .NET Word दस्तावेज़ों के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली और लचीला API प्रदान करता है, जिससे आप आसानी से गतिशील और आकर्षक चार्ट बना सकते हैं।


### पूछे जाने वाले प्रश्न

#### प्रश्न 1. .NET के लिए Aspose.Words क्या है?
Aspose.Words for .NET एक लाइब्रेरी है जो डेवलपर्स को Word दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। यह Word दस्तावेज़ों को बनाने, उनमें हेरफेर करने और सहेजने के लिए कई तरह की सुविधाएँ और कार्यक्षमताएँ प्रदान करता है।

#### प्रश्न 2. मैं .NET के लिए Aspose.Words कैसे स्थापित कर सकता हूँ?
.NET के लिए Aspose.Words को इंस्टॉल करने के लिए, आप Visual Studio में NuGet पैकेज मैनेजर का उपयोग कर सकते हैं। बस NuGet पैकेज मैनेजर में "Aspose.Words" खोजें और इसे अपने प्रोजेक्ट में इंस्टॉल करें।

#### प्रश्न 3. क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Words का उपयोग कर सकता हूँ?
नहीं, Aspose.Words for .NET खास तौर पर .NET एप्लीकेशन के लिए डिज़ाइन किया गया है। यह C# और VB.NET जैसी प्रोग्रामिंग भाषाओं के साथ काम करता है।

#### प्रश्न 4. क्या .NET के लिए Aspose.Words का उपयोग करने के लिए कोई अन्य पूर्वापेक्षाएँ हैं?
Aspose.Words for .NET लाइब्रेरी को इंस्टॉल करने के अलावा, आपको C# प्रोग्रामिंग और Word दस्तावेज़ों के साथ Words Processing का बुनियादी ज्ञान होना चाहिए। .NET फ्रेमवर्क से परिचित होना भी मददगार होगा।
