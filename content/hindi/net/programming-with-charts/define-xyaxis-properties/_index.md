---
title: एक चार्ट में XY अक्ष गुणों को परिभाषित करें
linktitle: एक चार्ट में XY अक्ष गुणों को परिभाषित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके चार्ट में XY अक्ष गुणों को परिभाषित करना सीखें। एक्स और वाई अक्षों के लिए अनुकूलन विकल्प प्रदर्शित किए गए हैं।
type: docs
weight: 10
url: /hi/net/programming-with-charts/define-xyaxis-properties/
---

यह ट्यूटोरियल बताता है कि चार्ट में X और Y अक्षों के गुणों को परिभाषित करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि चार्ट कैसे बनाया जाए, श्रृंखला डेटा कैसे जोड़ा जाए और अक्ष गुणों को कैसे अनुकूलित किया जाए।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे इंस्टॉल करने के लिए NuGet पैकेज मैनेजर का उपयोग करके इसे डाउनलोड कर सकते हैं।
- एक दस्तावेज़ निर्देशिका पथ जहां आउटपुट दस्तावेज़ सहेजा जाएगा।

## चरण 2: एक नया दस्तावेज़ बनाएं और एक चार्ट डालें।

 कोई नया बनाएं`Document` वस्तु और ए`DocumentBuilder` दस्तावेज़ बनाने के लिए.

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 इसके बाद, का उपयोग करके दस्तावेज़ में एक चार्ट डालें`InsertChart` की विधि`DocumentBuilder`. इस उदाहरण में, हम एक क्षेत्र चार्ट सम्मिलित करेंगे।

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## चरण 3: चार्ट में श्रृंखला डेटा जोड़ें

चार्ट में श्रृंखला डेटा जोड़ें. इस उदाहरण में, हम संबंधित तिथियों और मानों के साथ पांच डेटा बिंदु जोड़ेंगे।

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

## चरण 4: X और Y अक्ष गुणों को अनुकूलित करें

 एक्स और वाई अक्षों के गुणों को अनुकूलित करने के लिए, तक पहुंचें`ChartAxis` चार्ट से संबद्ध वस्तुएं.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 के गुणों को संशोधित करें`xAxis` और`yAxis`एक्स और वाई अक्षों के लिए वांछित विकल्प सेट करने के लिए ऑब्जेक्ट। इस उदाहरण में, हम कुछ सामान्य गुण प्रदर्शित करेंगे जिन्हें अनुकूलित किया जा सकता है।

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

 अंत में, का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके चार्ट में XY अक्ष गुणों को परिभाषित करने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके XYAxis Properties को परिभाषित करने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
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
	// X अक्ष को दिनांक के बजाय श्रेणी में बदलें, इसलिए सभी बिंदु X अक्ष पर समान अंतराल के साथ रखे जाएंगे।
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // अक्ष (सैकड़ों) की प्रदर्शन इकाइयों में मापा गया।
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

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट में X और Y अक्षों के लिए गुणों को कैसे परिभाषित किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक चार्ट बना सकते हैं, श्रृंखला डेटा जोड़ सकते हैं, और अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए अक्ष गुणों को अनुकूलित कर सकते हैं। .NET के लिए Aspose.Words Word दस्तावेज़ों में चार्ट के साथ वर्ड प्रोसेसिंग के लिए एक व्यापक एपीआई प्रदान करता है, जो आपको अक्षों सहित चार्ट के विभिन्न पहलुओं में हेरफेर करने की अनुमति देता है।

तक पहुंच कर`ChartAxis` चार्ट से जुड़े ऑब्जेक्ट, आप श्रेणी प्रकार, अक्ष क्रॉस, टिक चिह्न, लेबल स्थिति, स्केलिंग और बहुत कुछ जैसे गुणों को संशोधित कर सकते हैं। यह लचीलापन आपको अपने डेटा को प्रभावी ढंग से प्रस्तुत करने के लिए चार्ट के अक्षों की उपस्थिति और व्यवहार को अनुकूलित करने में सक्षम बनाता है।

.NET के लिए Aspose.Words का उपयोग करके, आप अपने .NET अनुप्रयोगों में चार्ट निर्माण और अनुकूलन क्षमताओं को सहजता से एकीकृत कर सकते हैं और समृद्ध विज़ुअलाइज़ेशन के साथ पेशेवर दिखने वाले दस्तावेज़ों की पीढ़ी को स्वचालित कर सकते हैं।

### पूछे जाने वाले प्रश्न

#### Q1. .NET के लिए Aspose.Words क्या है?
.NET के लिए Aspose.Words एक शक्तिशाली दस्तावेज़ प्रसंस्करण लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से Word दस्तावेज़ बनाने, हेरफेर करने और सहेजने में सक्षम बनाता है। यह चार्ट सहित दस्तावेज़ तत्वों के साथ वर्ड प्रोसेसिंग के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

#### Q2. मैं .NET के लिए Aspose.Words कैसे स्थापित कर सकता हूँ?
आप विजुअल स्टूडियो में NuGet पैकेज मैनेजर का उपयोग करके इसे डाउनलोड करके .NET के लिए Aspose.Words इंस्टॉल कर सकते हैं। बस NuGet पैकेज मैनेजर में "Apose.Words" खोजें और इसे अपने प्रोजेक्ट में इंस्टॉल करें।

#### Q3. क्या मैं .NET के लिए Aspose.Words का उपयोग करके चार्ट के अन्य पहलुओं को अनुकूलित कर सकता हूँ?
हां, .NET के लिए Aspose.Words चार्ट के विभिन्न पहलुओं को अनुकूलित करने के लिए व्यापक क्षमताएं प्रदान करता है। अक्ष गुणों को परिभाषित करने के अलावा, आप चार्ट प्रकार, डेटा श्रृंखला, किंवदंती, शीर्षक, प्लॉट क्षेत्र, डेटा लेबल और चार्ट के कई अन्य तत्वों को संशोधित कर सकते हैं। एपीआई चार्ट उपस्थिति और व्यवहार पर सूक्ष्म नियंत्रण प्रदान करता है।

#### Q4. क्या मैं .NET के लिए Aspose.Words का उपयोग करके विभिन्न प्रकार के चार्ट बना सकता हूँ?
 हां, .NET के लिए Aspose.Words क्षेत्र, बार, लाइन, पाई, स्कैटर और बहुत कुछ सहित चार्ट प्रकारों की एक विस्तृत श्रृंखला का समर्थन करता है। आप इसका उपयोग कर सकते हैं`ChartType` Word दस्तावेज़ में चार्ट आकार सम्मिलित करते समय वांछित चार्ट प्रकार निर्दिष्ट करने के लिए गणना।

#### Q5. क्या मैं चार्ट को विभिन्न प्रारूपों में सहेज सकता हूँ?
हां, .NET के लिए Aspose.Words आपको चार्ट वाले दस्तावेज़ को DOCX, PDF, HTML और अन्य जैसे विभिन्न स्वरूपों में सहेजने की अनुमति देता है। आप अपनी आवश्यकताओं के आधार पर उपयुक्त प्रारूप चुन सकते हैं और इसका उपयोग कर सकते हैं`Save` की विधि`Document` दस्तावेज़ को सहेजने के लिए ऑब्जेक्ट।

#### Q6. क्या मैं इन तकनीकों को किसी दस्तावेज़ में एकाधिक चार्ट पर लागू कर सकता हूँ?
 हां, आप प्रत्येक चार्ट के लिए आवश्यक चरणों को दोहराकर इन तकनीकों को किसी दस्तावेज़ में एकाधिक चार्ट पर लागू कर सकते हैं। आप अलग बना सकते हैं`Chart` और`ChartAxis` प्रत्येक चार्ट के लिए ऑब्जेक्ट बनाएं और उनके गुणों को तदनुसार अनुकूलित करें। .NET के लिए Aspose.Words एक ही दस्तावेज़ में एकाधिक चार्ट के साथ वर्ड प्रोसेसिंग के लिए पूर्ण समर्थन प्रदान करता है।