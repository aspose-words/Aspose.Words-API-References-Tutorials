---
title: किसी चार्ट के अक्ष में दिनांक समय मान जोड़ें
linktitle: किसी चार्ट के अक्ष में दिनांक समय मान जोड़ें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके चार्ट के अक्ष पर दिनांक समय मान जोड़ने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/date-time-values-to-axis/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट के अक्ष पर दिनांक समय मान कैसे जोड़ें।

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

## चरण 3: एक चार्ट आकार डालें और कॉन्फ़िगर करें
 का उपयोग करके दस्तावेज़ में एक चार्ट आकार डालें`InsertChart` की विधि`DocumentBuilder` वस्तु। वांछित चार्ट प्रकार और आयाम सेट करें।

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## चरण 4: चार्ट में डेटा जोड़ें
दिनांक समय मान सहित चार्ट श्रृंखला में डेटा जोड़ें।

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## चरण 5: अक्ष को कॉन्फ़िगर करें
दिनांक समय मान प्रदर्शित करने के लिए चार्ट के एक्स-अक्ष को कॉन्फ़िगर करें।

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## चरण 6: दस्तावेज़ सहेजें
 का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` तरीका। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithCharts.DateTimeValuesToAxis.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके एक्सिस के लिए दिनांक समय मान के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// प्रमुख इकाइयों को एक सप्ताह और छोटी इकाइयों को एक दिन पर सेट करें।
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

यह उदाहरण कोड एक नया वर्ड दस्तावेज़ बनाता है, एक्स-अक्ष पर दिनांक समय मानों के साथ एक कॉलम चार्ट सम्मिलित करता है, और दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजता है।

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट के अक्ष पर दिनांक समय मान कैसे जोड़ें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक चार्ट बना सकते हैं, श्रृंखला में दिनांक समय मान जोड़ सकते हैं, और दिनांक समय मान सटीक रूप से प्रदर्शित करने के लिए अक्ष को कॉन्फ़िगर कर सकते हैं। .NET के लिए Aspose.Words Word दस्तावेज़ों में चार्ट के साथ Words प्रोसेसिंग के लिए सुविधाओं का एक शक्तिशाली सेट प्रदान करता है, जो आपको दिनांक समय मानों के साथ डेटा को प्रभावी ढंग से प्रस्तुत करने और कल्पना करने की अनुमति देता है।

### पूछे जाने वाले प्रश्न

#### Q1. क्या मैं .NET के लिए Aspose.Words का उपयोग करके चार्ट के अक्ष पर दिनांक समय मान जोड़ सकता हूँ?
हाँ, .NET के लिए Aspose.Words के साथ, आप Word दस्तावेज़ में चार्ट के अक्ष पर दिनांक समय मान जोड़ और प्रदर्शित कर सकते हैं। Aspose.Words विभिन्न चार्ट प्रकारों के साथ काम करने और उनकी उपस्थिति को अनुकूलित करने के लिए एपीआई और कार्यक्षमता प्रदान करता है, जिसमें अक्ष पर दिनांक समय मानों को संभालना भी शामिल है।

#### Q2. मैं चार्ट श्रृंखला में दिनांक समय मान कैसे जोड़ूँ?
 चार्ट श्रृंखला में दिनांक समय मान जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`Add`चार्ट की श्रृंखला की विधि. संबंधित श्रृंखला मानों के साथ, श्रेणी (एक्स-अक्ष) डेटा के रूप में दिनांक समय मानों की एक सरणी प्रदान करें। यह आपको चार्ट पर दिनांक समय मानों के साथ डेटा बिंदु प्लॉट करने की अनुमति देता है।

#### Q3. मैं दिनांक समय मान प्रदर्शित करने के लिए अक्ष को कैसे कॉन्फ़िगर कर सकता हूं?
 आप उपयुक्त गुण सेट करके दिनांक समय मान प्रदर्शित करने के लिए चार्ट की धुरी को कॉन्फ़िगर कर सकते हैं। उदाहरण के लिए, आप इसका उपयोग करके अक्ष के लिए न्यूनतम और अधिकतम मान निर्दिष्ट कर सकते हैं`Scaling.Minimum` और`Scaling.Maximum` गुण, क्रमशः. इसके अतिरिक्त, आप अंतराल को परिभाषित करने और अक्ष के लिए टिक चिह्न निर्धारित करने के लिए प्रमुख और छोटी इकाइयाँ सेट कर सकते हैं।
