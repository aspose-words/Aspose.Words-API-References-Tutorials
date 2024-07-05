---
title: चार्ट डेटा लेबल अनुकूलित करें
linktitle: चार्ट डेटा लेबल अनुकूलित करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: डेटा बिंदुओं के बारे में अतिरिक्त जानकारी प्रदान करने के लिए .NET के लिए Aspose.Words का उपयोग करके चार्ट में डेटा लेबल जोड़ने और अनुकूलित करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/chart-data-label/
---

यह ट्यूटोरियल बताता है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट में डेटा लेबल कैसे जोड़ें और कस्टमाइज़ करें। डेटा लेबल चार्ट में डेटा बिंदुओं के बारे में अतिरिक्त जानकारी प्रदान करते हैं।

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
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## चरण 4: डेटा लेबल अनुकूलित करें
चार्ट श्रृंखला के डेटा लेबल संग्रह तक पहुंचें और डेटा लेबल की उपस्थिति को अनुकूलित करने के लिए विभिन्न गुणों को संशोधित करें।

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## चरण 5: दस्तावेज़ सहेजें
 दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` विधि। उचित फ़ाइल एक्सटेंशन के साथ वांछित फ़ाइल नाम प्रदान करें। इस उदाहरण में, हम दस्तावेज़ को "WorkingWithCharts.ChartDataLabel.docx" के रूप में सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके चार्ट डेटा लेबल के लिए उदाहरण स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// डिफ़ॉल्ट रूप से, जब आप पाई चार्ट में डेटा बिंदुओं में डेटा लेबल जोड़ते हैं, तो डेटा लेबल के लिए लीडर लाइनें प्रदर्शित होती हैं
	// डेटा बिंदुओं के अंत से बहुत दूर स्थित लीडर लाइनें डेटा लेबल और उसके बीच एक दृश्य कनेक्शन बनाती हैं
	// संबंधित डेटा बिंदु.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

बस! आपने Aspose.Words for .NET का उपयोग करके चार्ट में डेटा लेबल सफलतापूर्वक जोड़ और अनुकूलित कर लिया है।

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Words for .NET का उपयोग करके चार्ट में डेटा लेबल कैसे जोड़ें और कस्टमाइज़ करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप एक चार्ट सम्मिलित कर सकते हैं, डेटा लेबल संग्रह तक पहुँच सकते हैं, और डेटा लेबल की उपस्थिति को कस्टमाइज़ करने के लिए गुणों को संशोधित कर सकते हैं। Aspose.Words for .NET Word दस्तावेज़ों और चार्ट के साथ Words प्रोसेसिंग के लिए एक शक्तिशाली API प्रदान करता है, जिससे आप कस्टमाइज़ किए गए डेटा लेबल के साथ आकर्षक और जानकारीपूर्ण चार्ट बना सकते हैं।

### पूछे जाने वाले प्रश्न

#### प्रश्न 1. चार्ट में डेटा लेबल क्या हैं?
चार्ट में डेटा लेबल चार्ट में दर्शाए गए डेटा बिंदुओं के बारे में अतिरिक्त जानकारी प्रदान करते हैं। वे चार्ट के प्रकार और कॉन्फ़िगरेशन के आधार पर मान, श्रेणियाँ, श्रृंखला नाम, प्रतिशत या अन्य प्रासंगिक विवरण प्रदर्शित कर सकते हैं।

#### प्रश्न 2. क्या मैं डेटा लेबल के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप चार्ट में डेटा लेबल की उपस्थिति को अनुकूलित कर सकते हैं। Aspose.Words for .NET डेटा लेबल के विभिन्न गुणों को संशोधित करने के विकल्प प्रदान करता है, जैसे कि लीजेंड कुंजियाँ, लीडर लाइन, श्रेणी नाम, श्रृंखला नाम, मान और बहुत कुछ दिखाना। आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए विभाजक भी सेट कर सकते हैं और लेबल को प्रारूपित कर सकते हैं।

#### प्रश्न 3. क्या मैं किसी भी चार्ट प्रकार में डेटा लेबल जोड़ सकता हूँ?
हां, आप विभिन्न प्रकार के चार्ट में डेटा लेबल जोड़ सकते हैं, जिसमें बार चार्ट, पाई चार्ट, लाइन चार्ट और बहुत कुछ शामिल हैं। डेटा लेबल जोड़ने और कस्टमाइज़ करने की प्रक्रिया चार्ट के प्रकार और आपके द्वारा उपयोग की जा रही लाइब्रेरी या टूल के आधार पर थोड़ी भिन्न हो सकती है।
