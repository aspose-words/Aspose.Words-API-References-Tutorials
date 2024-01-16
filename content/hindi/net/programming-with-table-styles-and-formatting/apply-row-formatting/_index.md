---
title: पंक्ति स्वरूपण लागू करें
linktitle: पंक्ति स्वरूपण लागू करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके तालिका में पंक्ति स्वरूपण लागू करने के लिए चरण दर चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका में पंक्ति फ़ॉर्मेटिंग लागू करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत तक, आपको .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में तालिका पंक्तियों को प्रारूपित करने की स्पष्ट समझ हो जाएगी।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
सबसे पहले, आपको अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करना होगा। यह वह स्थान है जहां आप अपने संपादित Word दस्तावेज़ को सहेजना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: एक नया दस्तावेज़ और दस्तावेज़ निर्माता बनाएं
 इसके बाद, आपको इसका एक नया उदाहरण बनाना होगा`Document` क्लास और उस दस्तावेज़ के लिए एक दस्तावेज़ निर्माता।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक नया बोर्ड प्रारंभ करें
 पंक्ति स्वरूपण लागू करने के लिए, हमें पहले इसका उपयोग करके एक नई तालिका प्रारंभ करनी होगी`StartTable()` दस्तावेज़ निर्माता की विधि.

```csharp
Table table = builder. StartTable();
```

## चरण 4: सेल डालें और पंक्ति प्रारूप पर जाएं
अब हम तालिका में एक सेल सम्मिलित कर सकते हैं और दस्तावेज़ बिल्डर का उपयोग करके उस सेल के लिए पंक्ति प्रारूप तक पहुंच सकते हैं`InsertCell()` और`RowFormat` तरीके.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## चरण 5: पंक्ति की ऊँचाई निर्धारित करें
 पंक्ति की ऊंचाई निर्धारित करने के लिए, हम इसका उपयोग करते हैं`Height` और`HeightRule` पंक्ति प्रारूप के गुण. इस उदाहरण में, हम 100 बिंदुओं की एक पंक्ति की ऊंचाई निर्धारित करते हैं और इसका उपयोग करते हैं`Exactly` नियम।

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## चरण 6: तालिका स्वरूपण को परिभाषित करें
 कुछ स्वरूपण गुणों को तालिका पर ही सेट किया जा सकता है और सभी तालिका पंक्तियों पर लागू किया जा सकता है। इस उदाहरण में, हम तालिका मार्जिन गुणों का उपयोग करके सेट करते हैं`LeftPadding`, `RightPadding`, `TopPadding` और`BottomPadding` गुण।

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## चरण 7: पंक्ति में सामग्री जोड़ें
अब हम कर सकते हैं

 हम दस्तावेज़ कंस्ट्रक्टर के तरीकों का उपयोग करके लाइन में सामग्री जोड़ने जा रहे हैं। इस उदाहरण में, हम इसका उपयोग करते हैं`Writeln()` लाइन में टेक्स्ट जोड़ने की विधि.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## चरण 8: पंक्ति और तालिका समाप्त करें
 एक बार जब हम सामग्री को पंक्ति में जोड़ लेते हैं, तो हम इसका उपयोग करके पंक्ति को समाप्त कर सकते हैं`EndRow()` विधि और फिर का उपयोग करके तालिका को समाप्त करें`EndTable()` तरीका।

```csharp
builder. EndRow();
builder. EndTable();
```

## चरण 9: संशोधित दस्तावेज़ सहेजें
अंत में, हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं। आप आउटपुट दस्तावेज़ के लिए उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

बधाई हो! अब आपने .NET के लिए Aspose.Words का उपयोग करके तालिका में पंक्ति स्वरूपण लागू कर दिया है।

### .NET के लिए Aspose.Words का उपयोग करके पंक्ति फ़ॉर्मेटिंग लागू करने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// ये स्वरूपण गुण तालिका पर सेट किए गए हैं और तालिका की सभी पंक्तियों पर लागू किए गए हैं।
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके तालिका में पंक्ति स्वरूपण कैसे लागू किया जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इस कार्यक्षमता को अपने C# प्रोजेक्ट में आसानी से एकीकृत कर सकते हैं। तालिका पंक्ति स्वरूपण में हेरफेर दस्तावेज़ प्रसंस्करण का एक अनिवार्य पहलू है, और Aspose.Words इसे प्राप्त करने के लिए एक शक्तिशाली और लचीला एपीआई प्रदान करता है। इस ज्ञान से, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति में सुधार कर सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।