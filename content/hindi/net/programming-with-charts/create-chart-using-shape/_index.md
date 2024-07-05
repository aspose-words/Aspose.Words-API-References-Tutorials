---
title: आकृति का उपयोग करके चार्ट बनाएं और अनुकूलित करें
linktitle: आकृति का उपयोग करके चार्ट बनाएं और अनुकूलित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में आकृति का उपयोग करके चार्ट बनाना और उसे अनुकूलित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/create-chart-using-shape/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में आकृति का उपयोग करके चार्ट कैसे बनाया जाए।

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

## चरण 3: चार्ट आकार डालें और कॉन्फ़िगर करें
 दस्तावेज़ में चार्ट आकार डालें`InsertChart` की विधि`DocumentBuilder` ऑब्जेक्ट. इच्छित चार्ट प्रकार और आयाम सेट करें.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## चरण 4: चार्ट को अनुकूलित करें
चार्ट शीर्षक और लेजेंड जैसे विभिन्न गुणों को संशोधित करके चार्ट को अनुकूलित करें।

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## चरण 5: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithCharts.CreateChartUsingShape.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके आकृति का उपयोग करके चार्ट बनाने के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// कृपया ध्यान दें कि यदि शीर्षक पाठ के रूप में शून्य या रिक्त मान निर्दिष्ट किया गया है, तो स्वचालित रूप से उत्पन्न शीर्षक दिखाया जाएगा।
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

बस! आपने Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में आकृति का उपयोग करके सफलतापूर्वक एक चार्ट बना लिया है।

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Words for .NET का उपयोग करके Word दस्तावेज़ में आकृति का उपयोग करके चार्ट कैसे बनाया जाता है। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप चार्ट आकृति सम्मिलित और कॉन्फ़िगर कर सकते हैं, इसकी उपस्थिति को अनुकूलित कर सकते हैं, और दस्तावेज़ को सहेज सकते हैं। Aspose.Words for .NET Word दस्तावेज़ों और चार्ट के साथ Words प्रोसेसिंग के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है, जिससे आप सीधे अपने .NET अनुप्रयोगों में पेशेवर दिखने वाले और आकर्षक चार्ट बना सकते हैं।

### पूछे जाने वाले प्रश्न

#### प्रश्न 1. क्या मैं .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में चार्ट बना सकता हूँ?
हां, .NET के लिए Aspose.Words के साथ, आप प्रोग्रामेटिक रूप से Word दस्तावेज़ में चार्ट बना सकते हैं। Aspose.Words विभिन्न प्रकार के चार्ट सम्मिलित करने, उनकी उपस्थिति को अनुकूलित करने और चार्ट डेटा में हेरफेर करने के लिए API और कार्यक्षमता प्रदान करता है।

#### प्रश्न 2. .NET के लिए Aspose.Words द्वारा कौन से चार्ट प्रकार समर्थित हैं?
Aspose.Words for .NET चार्ट प्रकारों की एक विस्तृत श्रृंखला का समर्थन करता है, जिसमें लाइन चार्ट, बार चार्ट, पाई चार्ट, क्षेत्र चार्ट, स्कैटर चार्ट और बहुत कुछ शामिल है। आप अपने डेटा और विज़ुअलाइज़ेशन आवश्यकताओं के आधार पर उपयुक्त चार्ट प्रकार चुन सकते हैं।

#### प्रश्न 3. क्या मैं बनाए गए चार्ट के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप .NET के लिए Aspose.Words का उपयोग करके बनाए गए चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। आप अपनी विशिष्ट डिज़ाइन और फ़ॉर्मेटिंग आवश्यकताओं को पूरा करने के लिए चार्ट शीर्षक, लेजेंड स्थिति, डेटा लेबल, अक्ष लेबल, रंग और अन्य विज़ुअल तत्वों जैसे गुणों को संशोधित कर सकते हैं।
