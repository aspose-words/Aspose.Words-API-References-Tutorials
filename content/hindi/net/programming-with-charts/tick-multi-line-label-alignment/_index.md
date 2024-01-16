---
title: एक चार्ट में मल्टी लाइन लेबल संरेखण पर निशान लगाएं
linktitle: एक चार्ट में मल्टी लाइन लेबल संरेखण पर निशान लगाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके चार्ट अक्ष में टिक मल्टी-लाइन लेबल को संरेखित करना सीखें।
type: docs
weight: 10
url: /hi/net/programming-with-charts/tick-multi-line-label-alignment/
---

यह ट्यूटोरियल बताता है कि चार्ट अक्ष में टिक मल्टी-लाइन लेबल के संरेखण को सेट करने के लिए .NET के लिए Aspose.Words का उपयोग कैसे करें। प्रदान किया गया स्रोत कोड दर्शाता है कि चार्ट कैसे बनाएं, अक्ष तक कैसे पहुंचें और टिक लेबल संरेखण को कैसे संशोधित करें।

## चरण 1: प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

- .NET लाइब्रेरी के लिए Aspose.Words स्थापित। आप इसे इंस्टॉल करने के लिए NuGet पैकेज मैनेजर का उपयोग करके इसे डाउनलोड कर सकते हैं।
- एक दस्तावेज़ निर्देशिका पथ जहां आउटपुट दस्तावेज़ सहेजा जाएगा।

## चरण 2: एक नया दस्तावेज़ बनाएं और एक चार्ट डालें

 कोई नया बनाएं`Document` वस्तु और ए`DocumentBuilder` दस्तावेज़ बनाने के लिए.

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 अगला, का उपयोग करें`InsertChart` की विधि`DocumentBuilder` दस्तावेज़ में स्कैटर चार्ट सम्मिलित करने के लिए।

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## चरण 3: टिक लेबल संरेखण सेट करें

 टिक मल्टी-लाइन लेबल का संरेखण सेट करने के लिए, एक्सेस करें`AxisX` चार्ट की संपत्ति और सेट करें`TickLabelAlignment` वांछित संरेखण के लिए संपत्ति। इस उदाहरण में, हम संरेखण को सेट करते हैं`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## चरण 4: दस्तावेज़ सहेजें

 अंत में, का उपयोग करके दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजें`Save` की विधि`Document` वस्तु।

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

यह .NET के लिए Aspose.Words का उपयोग करके टिक मल्टी-लाइन लेबल संरेखण सेट करने का कार्यान्वयन पूरा करता है।

### .NET के लिए Aspose.Words का उपयोग करके टिक मल्टी लाइन लेबल संरेखण के लिए उदाहरण स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// यह गुण केवल मल्टी-लाइन लेबल के लिए प्रभावी है।
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.Words का उपयोग करके चार्ट अक्ष में टिक मल्टी-लाइन लेबल का संरेखण कैसे सेट किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड का उपयोग करके, आप एक नया दस्तावेज़ बना सकते हैं, एक स्कैटर चार्ट सम्मिलित कर सकते हैं, चार्ट अक्ष तक पहुंच सकते हैं, और टिक लेबल संरेखण को संशोधित कर सकते हैं।

.NET के लिए Aspose.Words Word दस्तावेज़ों में चार्ट में हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। टिक मल्टी-लाइन लेबल तब उपयोगी होते हैं जब अक्ष लेबल में लंबा टेक्स्ट होता है जिसे कई लाइनों में लपेटने या विभाजित करने की आवश्यकता होती है। टिक लेबल संरेखण सेट करके, आप इष्टतम प्रस्तुति और पठनीयता सुनिश्चित करते हुए, चार्ट अक्ष के भीतर मल्टी-लाइन लेबल के क्षैतिज संरेखण को नियंत्रित कर सकते हैं।

टिक मल्टी-लाइन लेबल संरेखण को अनुकूलित करने से आप अपने चार्ट की उपस्थिति को ठीक कर सकते हैं, खासकर जब लंबे या जटिल लेबल से निपटते हैं। लेबल को दाएं, बाएं, केंद्र या उचित दिशा में संरेखित करके, आप अक्ष के साथ टिक लेबल की एक संतुलित और दृष्टि से आकर्षक व्यवस्था प्राप्त कर सकते हैं।

.NET के लिए Aspose.Words के साथ, आप चार्ट अक्ष की टिक लेबल संरेखण संपत्ति को आसानी से एक्सेस और संशोधित कर सकते हैं, जो आपको आपके वर्ड दस्तावेज़ चार्ट में टिक लेबल की उपस्थिति और लेआउट पर पूर्ण नियंत्रण प्रदान करता है।

### पूछे जाने वाले प्रश्न

#### Q1. चार्ट अक्ष में टिक मल्टी-लाइन लेबल क्या हैं?
चार्ट अक्ष में बहु-पंक्ति लेबल पर टिक करें, अक्ष लेबल को संदर्भित करता है जो कई पंक्तियों में फैला होता है जब लेबल टेक्स्ट लंबा होता है या उपलब्ध स्थान के भीतर फिट होने के लिए रैपिंग की आवश्यकता होती है। लेबल टेक्स्ट को छोटा करने या दृश्य अव्यवस्था पैदा करने के बजाय, पठनीयता सुनिश्चित करने के लिए चार्ट अक्ष स्वचालित रूप से लेबल को कई पंक्तियों में विभाजित करता है। चार्ट में लंबी श्रेणी या मूल्य लेबल से निपटने के दौरान टिक मल्टी-लाइन लेबल विशेष रूप से उपयोगी होते हैं।

#### Q2. क्या मैं चार्ट अक्ष में टिक लेबल के संरेखण को अनुकूलित कर सकता हूँ?
 हाँ, आप .NET के लिए Aspose.Words का उपयोग करके चार्ट अक्ष में टिक लेबल के संरेखण को अनुकूलित कर सकते हैं। तक पहुंच कर`TickLabelAlignment` की संपत्ति`ChartAxis` ऑब्जेक्ट, आप टिक लेबल के लिए वांछित संरेखण सेट कर सकते हैं। संरेखण विकल्पों में बाएँ, दाएँ, मध्य या उचित संरेखण शामिल हैं। संरेखण को समायोजित करने से आप चार्ट अक्ष के साथ टिक लेबल की क्षैतिज स्थिति को नियंत्रित कर सकते हैं, जिससे उचित पठनीयता और दृश्य प्रस्तुति सुनिश्चित होती है।

#### Q3. मुझे चार्ट अक्ष में टिक लेबल संरेखण को बदलने पर कब विचार करना चाहिए?
चार्ट अक्ष में टिक लेबल संरेखण को बदलना तब फायदेमंद होता है जब आपके पास लंबे या बहु-पंक्ति लेबल होते हैं जिनके लिए इष्टतम प्रस्तुति और पठनीयता की आवश्यकता होती है। संरेखण को समायोजित करके, आप यह सुनिश्चित कर सकते हैं कि ओवरलैपिंग या कटौती से बचने के लिए लेबल ठीक से संरेखित और दूरी पर हैं। लंबे श्रेणी के नाम, वर्बोज़ मान लेबल, या किसी अन्य परिदृश्य वाले चार्ट से निपटने के दौरान टिक लेबल संरेखण को बदलने पर विचार करें जहां डिफ़ॉल्ट संरेखण वांछित दृश्य उपस्थिति प्रदान नहीं करता है।

#### Q4. क्या टिक लेबल संरेखण चार्ट अक्ष में एकल-पंक्ति लेबल को प्रभावित करता है?
नहीं, टिक लेबल संरेखण गुण चार्ट अक्ष में एकल-पंक्ति लेबल को प्रभावित नहीं करता है। यह विशेष रूप से मल्टी-लाइन लेबल के लिए डिज़ाइन किया गया है जिन्हें लपेटने या विभाजित करने की आवश्यकता होती है। एकल-पंक्ति लेबल चार्ट अक्ष की डिफ़ॉल्ट संरेखण सेटिंग्स के आधार पर संरेखित होते हैं। टिक लेबल संरेखण गुण केवल उन लेबलों पर लागू होता है जो कई पंक्तियों में फैले होते हैं, जिससे आप मल्टी-लाइन लेबल के भीतर प्रत्येक पंक्ति के संरेखण को नियंत्रित कर सकते हैं।

#### Q5. क्या मैं चार्ट में एक्स-अक्ष और वाई-अक्ष के लिए टिक लेबल को अलग-अलग संरेखित कर सकता हूं?
 हाँ, आप .NET के लिए Aspose.Words का उपयोग करके चार्ट में X-अक्ष और Y-अक्ष के लिए टिक लेबल को अलग-अलग संरेखित कर सकते हैं। टिक लेबल संरेखण गुण प्रत्येक चार्ट अक्ष के लिए विशिष्ट है। संबंधित तक पहुंच कर`ChartAxis` एक्स-अक्ष या वाई-अक्ष के लिए ऑब्जेक्ट, आप स्वतंत्र रूप से टिक लेबल संरेखण को विभिन्न मानों पर सेट कर सकते हैं। यह आपको चार्ट में प्रत्येक अक्ष के लिए आपकी विशिष्ट आवश्यकताओं के आधार पर टिक लेबल को अलग-अलग संरेखित करने की सुविधा प्रदान करता है।