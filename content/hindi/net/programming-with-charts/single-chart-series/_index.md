---
title: एक चार्ट में एकल चार्ट श्रृंखला को अनुकूलित करें
linktitle: एक चार्ट में एकल चार्ट श्रृंखला को अनुकूलित करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके चार्ट में एकल चार्ट श्रृंखला को अनुकूलित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/single-chart-series/
---

यह ट्यूटोरियल बताता है कि चार्ट में एकल चार्ट श्रृंखला को अनुकूलित करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि चार्ट कैसे बनाएं, विशिष्ट श्रृंखला तक कैसे पहुंचें और उनके गुणों को कैसे संशोधित करें।

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

 अगला, का उपयोग करें`InsertChart` की विधि`DocumentBuilder` दस्तावेज़ में एक लाइन चार्ट सम्मिलित करने के लिए।

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## चरण 3: चार्ट श्रृंखला तक पहुंचें और अनुकूलित करें

 एकल चार्ट श्रृंखला को संशोधित करने के लिए, आपको इसका उपयोग करना होगा`ChartSeries` चार्ट के ऑब्जेक्ट.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## चरण 4: दस्तावेज़ सहेजें

 अंत में, का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके एकल चार्ट श्रृंखला को अनुकूलित करने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके एकल चार्ट श्रृंखला के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// आप यह भी निर्दिष्ट कर सकते हैं कि चार्ट पर बिंदुओं को जोड़ने वाली रेखा को कैटमुल-रोम स्प्लिंस का उपयोग करके चिकना किया जाएगा या नहीं।
	series0.Smooth = true;
	series1.Smooth = true;
	// निर्दिष्ट करता है कि यदि मान ऋणात्मक है तो डिफ़ॉल्ट रूप से मूल तत्व अपने रंगों को उलट देगा या नहीं।
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि .NET के लिए Aspose.Words का उपयोग करके चार्ट में एकल चार्ट श्रृंखला को कैसे अनुकूलित किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, आप एक नया दस्तावेज़ बना सकते हैं, एक लाइन चार्ट सम्मिलित कर सकते हैं, विशिष्ट चार्ट श्रृंखला तक पहुंच सकते हैं, और वांछित अनुकूलन प्राप्त करने के लिए उनके गुणों को संशोधित कर सकते हैं।

.NET के लिए Aspose.Words Word दस्तावेज़ों में चार्ट में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। व्यक्तिगत चार्ट श्रृंखला तक पहुंच कर, आप उनके स्वरूप और व्यवहार को अनुकूलित करने के लिए विशिष्ट संशोधन लागू कर सकते हैं। यह आपको अपने चार्ट के दृश्य प्रतिनिधित्व को बढ़ाने के लिए श्रृंखला का नाम बदलने, चार्ट लाइन को सुचारू करने, डेटा बिंदुओं के लिए मार्करों को अनुकूलित करने, नकारात्मक मानों के लिए रंगों को उलटने और बहुत कुछ करने की अनुमति देता है।

एकल चार्ट श्रृंखला को अनुकूलित करने से आपको विशिष्ट डेटा को हाइलाइट करने या अपने चार्ट के भीतर विशेष रुझानों पर जोर देने की सुविधा मिलती है। .NET के लिए Aspose.Words के साथ, आप चार्ट श्रृंखला गुणों तक आसानी से पहुंच और संशोधित कर सकते हैं, जिससे आप अपने Word दस्तावेज़ों में दृश्यमान रूप से आकर्षक और जानकारीपूर्ण चार्ट बना सकते हैं।

### पूछे जाने वाले प्रश्न

#### Q1. क्या मैं एक चार्ट में एकाधिक चार्ट श्रृंखला को अनुकूलित कर सकता हूँ?
 हाँ, आप .NET के लिए Aspose.Words का उपयोग करके एक चार्ट में एकाधिक चार्ट श्रृंखला को अनुकूलित कर सकते हैं। तक पहुंच कर`ChartSeries`चार्ट के भीतर ऑब्जेक्ट, आप उनके सूचकांकों या विशिष्ट मानदंडों के आधार पर कई श्रृंखलाओं का चयन और संशोधन कर सकते हैं। प्रत्येक चार्ट श्रृंखला के लिए वांछित गुणों को संशोधित करने के लिए एक लूप या व्यक्तिगत असाइनमेंट का उपयोग करें। इस तरह, आप एक ही चार्ट के भीतर कई श्रृंखलाओं में अलग-अलग अनुकूलन लागू कर सकते हैं।

#### Q2. मैं चार्ट श्रृंखला का नाम कैसे बदल सकता हूँ?
 .NET के लिए Aspose.Words का उपयोग करके चार्ट में चार्ट श्रृंखला का नाम बदलने के लिए, आपको एक्सेस करने की आवश्यकता है`Name` की संपत्ति`ChartSeries` ऑब्जेक्ट बनाएं और इसे वांछित नाम पर सेट करें। श्रृंखला का नाम आम तौर पर चार्ट लेजेंड या डेटा लेबल में प्रदर्शित होता है, जो श्रृंखला के लिए एक वर्णनात्मक लेबल प्रदान करता है। श्रृंखला के नाम को संशोधित करके, आप सार्थक नाम प्रदान कर सकते हैं जो प्रत्येक श्रृंखला द्वारा दर्शाए गए डेटा को प्रतिबिंबित करते हैं।

#### Q3. चार्ट सीरीज स्मूथिंग क्या है?
चार्ट श्रृंखला स्मूथिंग एक दृश्य वृद्धि तकनीक है जो आपको चार्ट पर बिंदुओं को जोड़ने वाली एक चिकनी रेखा बनाने की अनुमति देती है। यह डेटा बिंदुओं के बीच अंतरण करने और एक दृश्यमान सुखदायक वक्र बनाने के लिए कैटमुल-रोम स्प्लिंस जैसे एक स्मूथिंग एल्गोरिदम लागू करता है। .NET के लिए Aspose.Words का उपयोग करके चार्ट में श्रृंखला स्मूथिंग सक्षम करने के लिए, एक्सेस करें`Smooth` की संपत्ति`ChartSeries` ऑब्जेक्ट करें और इसे सेट करें`true`. अनियमित उतार-चढ़ाव वाले डेटा में रुझान या पैटर्न प्रदर्शित करने के लिए स्मूथिंग उपयोगी हो सकती है।

#### Q4. मैं चार्ट श्रृंखला में डेटा बिंदुओं के लिए मार्करों को कैसे अनुकूलित कर सकता हूं?
 .NET के लिए Aspose.Words का उपयोग करके चार्ट श्रृंखला में डेटा बिंदुओं के लिए मार्करों को अनुकूलित करने के लिए, आपको एक्सेस करने की आवश्यकता है`Marker` की संपत्ति`ChartSeries` ऑब्जेक्ट बनाएं और उसके गुणों को संशोधित करें जैसे कि`Symbol` और`Size`. मार्कर व्यक्तिगत डेटा बिंदुओं को दर्शाने के लिए चार्ट पर रखे गए दृश्य संकेतक हैं। आप विभिन्न प्रकार के अंतर्निहित मार्कर प्रतीकों में से चुन सकते हैं और श्रृंखला के भीतर विशिष्ट डेटा बिंदुओं को हाइलाइट करने या अलग करने के लिए उनके आकार को समायोजित कर सकते हैं।

#### Q5. क्या मैं चार्ट श्रृंखला में नकारात्मक मानों के लिए रंगों को उलट सकता हूँ?
 हां, आप .NET के लिए Aspose.Words का उपयोग करके चार्ट श्रृंखला में नकारात्मक मानों के लिए रंगों को उलट सकते हैं। सेटिंग करके`InvertIfNegative` की संपत्ति`ChartSeries` करने के लिए वस्तु`true`, नकारात्मक मान वाले डेटा बिंदुओं के रंग उलटे हो जाएंगे, जिससे वे सकारात्मक मानों से दृष्टिगत रूप से भिन्न हो जाएंगे। चार्ट श्रृंखला में सकारात्मक और नकारात्मक मूल्यों की तुलना करते समय यह सुविधा उपयोगी हो सकती है, जो दोनों के बीच स्पष्ट अंतर प्रदान करती है।