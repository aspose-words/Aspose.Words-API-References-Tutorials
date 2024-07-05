---
title: चार्ट में XY अक्ष गुण परिभाषित करें
linktitle: चार्ट में XY अक्ष गुण परिभाषित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके चार्ट में XY अक्ष गुणधर्मों को परिभाषित करना सीखें। X और Y अक्षों के लिए अनुकूलन विकल्प प्रदर्शित किए गए हैं।
type: docs
weight: 10
url: /hi/net/programming-with-charts/define-xyaxis-properties/
---

यह ट्यूटोरियल बताता है कि चार्ट में X और Y अक्षों के लिए गुण परिभाषित करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि चार्ट कैसे बनाया जाए, श्रृंखला डेटा कैसे जोड़ा जाए और अक्ष गुणों को कैसे अनुकूलित किया जाए।

## चरण 1: प्रोजेक्ट सेट अप करें

सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- Aspose.Words for .NET लाइब्रेरी स्थापित है। आप इसे स्थापित करने के लिए NuGet पैकेज मैनेजर का उपयोग करके डाउनलोड कर सकते हैं।
- दस्तावेज़ निर्देशिका पथ जहाँ आउटपुट दस्तावेज़ सहेजा जाएगा.

## चरण 2: एक नया दस्तावेज़ बनाएँ और एक चार्ट डालें

 कोई नया बनाएं`Document` वस्तु और एक`DocumentBuilder` दस्तावेज़ बनाने के लिए.

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 इसके बाद, दस्तावेज़ में एक चार्ट डालें`InsertChart` की विधि`DocumentBuilder`इस उदाहरण में, हम एक क्षेत्र चार्ट सम्मिलित करेंगे।

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## चरण 3: चार्ट में श्रृंखला डेटा जोड़ें

चार्ट में श्रृंखला डेटा जोड़ें। इस उदाहरण में, हम संगत दिनांकों और मानों के साथ पाँच डेटा बिंदु जोड़ेंगे।

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## चरण 4: X और Y अक्ष गुणधर्मों को अनुकूलित करें

 X और Y अक्षों के गुणों को अनुकूलित करने के लिए, एक्सेस करें`ChartAxis` चार्ट से संबद्ध ऑब्जेक्ट.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 के गुणों को संशोधित करें`xAxis` और`yAxis` और Y अक्षों के लिए वांछित विकल्प सेट करने के लिए ऑब्जेक्ट। इस उदाहरण में, हम कुछ सामान्य गुण प्रदर्शित करेंगे जिन्हें अनुकूलित किया जा सकता है।

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## चरण 5: दस्तावेज़ सहेजें

 अंत में, दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

इससे .NET के लिए Aspose.Words का उपयोग करके चार्ट में XY अक्ष गुणों को परिभाषित करने का कार्यान्वयन पूरा हो जाता है।

### .NET के लिए Aspose.Words का उपयोग करके XYAxis गुण परिभाषित करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// चार्ट डालें
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// एक्स अक्ष को दिनांक के स्थान पर श्रेणी में बदलें, जिससे सभी बिंदु एक्स अक्ष पर समान अंतराल पर रखे जाएंगे।
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //वाई अक्ष (सैकड़ों) की प्रदर्शन इकाइयों में मापा जाता है।
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Words for .NET का उपयोग करके चार्ट में X और Y अक्षों के लिए गुण कैसे परिभाषित करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक चार्ट बना सकते हैं, श्रृंखला डेटा जोड़ सकते हैं, और अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए अक्ष गुणों को अनुकूलित कर सकते हैं। Aspose.Words for .NET Word दस्तावेज़ों में चार्ट के साथ Words प्रोसेसिंग के लिए एक व्यापक API प्रदान करता है, जिससे आप अक्षों सहित चार्ट के विभिन्न पहलुओं में हेरफेर कर सकते हैं।

तक पहुंच कर`ChartAxis` चार्ट से जुड़े ऑब्जेक्ट्स, आप श्रेणी प्रकार, अक्ष क्रॉस, टिक मार्क, लेबल पोजिशन, स्केलिंग और अधिक जैसे गुणों को संशोधित कर सकते हैं। यह लचीलापन आपको अपने डेटा को प्रभावी ढंग से प्रस्तुत करने के लिए चार्ट के अक्षों की उपस्थिति और व्यवहार को अनुकूलित करने में सक्षम बनाता है।

.NET के लिए Aspose.Words का उपयोग करके, आप अपने .NET अनुप्रयोगों में चार्ट निर्माण और अनुकूलन क्षमताओं को सहजता से एकीकृत कर सकते हैं और समृद्ध विज़ुअलाइज़ेशन के साथ पेशेवर दिखने वाले दस्तावेज़ों के निर्माण को स्वचालित कर सकते हैं।

### पूछे जाने वाले प्रश्न

#### प्रश्न 1. .NET के लिए Aspose.Words क्या है?
Aspose.Words for .NET एक शक्तिशाली दस्तावेज़ प्रसंस्करण लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से Word दस्तावेज़ बनाने, हेरफेर करने और सहेजने में सक्षम बनाती है। यह चार्ट सहित दस्तावेज़ तत्वों के साथ Words प्रसंस्करण के लिए कई प्रकार की सुविधाएँ प्रदान करता है।

#### प्रश्न 2. मैं .NET के लिए Aspose.Words कैसे स्थापित कर सकता हूँ?
आप Visual Studio में NuGet पैकेज मैनेजर का उपयोग करके इसे डाउनलोड करके .NET के लिए Aspose.Words इंस्टॉल कर सकते हैं। बस NuGet पैकेज मैनेजर में "Aspose.Words" खोजें और इसे अपने प्रोजेक्ट में इंस्टॉल करें।

#### प्रश्न 3. क्या मैं .NET के लिए Aspose.Words का उपयोग करके चार्ट के अन्य पहलुओं को अनुकूलित कर सकता हूं?
हां, .NET के लिए Aspose.Words चार्ट के विभिन्न पहलुओं को अनुकूलित करने के लिए व्यापक क्षमताएं प्रदान करता है। अक्ष गुणों को परिभाषित करने के अलावा, आप चार्ट प्रकार, डेटा श्रृंखला, किंवदंती, शीर्षक, प्लॉट क्षेत्र, डेटा लेबल और चार्ट के कई अन्य तत्वों को संशोधित कर सकते हैं। API चार्ट की उपस्थिति और व्यवहार पर बारीक नियंत्रण प्रदान करता है।

#### प्रश्न 4. क्या मैं .NET के लिए Aspose.Words का उपयोग करके विभिन्न प्रकार के चार्ट बना सकता हूँ?
 हां, Aspose.Words for .NET चार्ट प्रकारों की एक विस्तृत श्रृंखला का समर्थन करता है, जिसमें क्षेत्र, बार, रेखा, पाई, स्कैटर और बहुत कुछ शामिल है। आप इसका उपयोग कर सकते हैं`ChartType` किसी वर्ड दस्तावेज़ में चार्ट आकार सम्मिलित करते समय वांछित चार्ट प्रकार निर्दिष्ट करने के लिए गणना।

#### प्रश्न 5. क्या मैं चार्ट को विभिन्न प्रारूपों में सहेज सकता हूँ?
हां, Aspose.Words for .NET आपको चार्ट वाले दस्तावेज़ को विभिन्न प्रारूपों में सहेजने की अनुमति देता है, जैसे कि DOCX, PDF, HTML, और अधिक। आप अपनी आवश्यकताओं के आधार पर उपयुक्त प्रारूप चुन सकते हैं और इसका उपयोग कर सकते हैं`Save` की विधि`Document` दस्तावेज़ को सहेजने के लिए ऑब्जेक्ट का उपयोग करें.

#### प्रश्न 6. क्या मैं इन तकनीकों को एक दस्तावेज़ में एकाधिक चार्ट पर लागू कर सकता हूँ?
 हां, आप प्रत्येक चार्ट के लिए आवश्यक चरणों को दोहराकर इन तकनीकों को दस्तावेज़ में कई चार्ट पर लागू कर सकते हैं। आप अलग-अलग चार्ट बना सकते हैं`Chart` और`ChartAxis` प्रत्येक चार्ट के लिए ऑब्जेक्ट्स और उनके गुणों को तदनुसार अनुकूलित करें। Aspose.Words for .NET एक ही दस्तावेज़ में कई चार्ट के साथ वर्ड प्रोसेसिंग के लिए पूर्ण समर्थन प्रदान करता है।