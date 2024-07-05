---
title: तालिका शैली बनाएँ
linktitle: तालिका शैली बनाएँ
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके कस्टम तालिका शैली बनाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/create-table-style/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके टेबल स्टाइल बनाने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को अपने स्वयं के प्रोजेक्ट में समझने और लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में अपनी टेबल के लिए कस्टम स्टाइल कैसे बनाएँ।

## चरण 1: दस्तावेज़ निर्देशिका निर्धारित करें
सबसे पहले, आपको अपने दस्तावेज़ निर्देशिका का पथ सेट करना होगा। यह वह स्थान है जहाँ आप अपना संपादित Word दस्तावेज़ सहेजना चाहते हैं। "आपके दस्तावेज़ निर्देशिका" को उचित पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: नया दस्तावेज़ और दस्तावेज़ निर्माता बनाएँ
 इसके बाद, आपको एक नया उदाहरण बनाना होगा`Document` क्लास और उस दस्तावेज़ के लिए एक दस्तावेज़ निर्माता।

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## चरण 3: एक नई तालिका शुरू करें और कक्ष जोड़ें
तालिका बनाना शुरू करने के लिए, हम उपयोग करते हैं`StartTable()` दस्तावेज़ बिल्डर की विधि, फिर हम तालिका में कोशिकाओं को जोड़ते हैं`InsertCell()` विधि और हम कोशिकाओं की सामग्री को का उपयोग करके लिखते हैं`Write()` तरीका।

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## चरण 4: तालिका शैली बनाएँ
 अब हम इसका उपयोग करके एक तालिका शैली बना सकते हैं`TableStyle` वर्ग और`Add()` दस्तावेज़ से विधि`s `स्टाइल्स` संग्रह। हम शैली के गुणों को परिभाषित करते हैं, जैसे कि बॉर्डर, मार्जिन और पैडिंग।

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## चरण 5: तालिका पर तालिका शैली लागू करें
 अंत में, हम अपने द्वारा बनाई गई तालिका शैली को तालिका पर लागू करते हैं`Style` तालिका की संपत्ति.

```csharp
table.Style = tableStyle;
```

## चरण 6: संशोधित दस्तावेज़ को सहेजें
अंत में संशोधित दस्तावेज़ को फ़ाइल में सहेजें। आप आउटपुट दस्तावेज़ के लिए उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

बधाई हो! आपने अब .NET के लिए Aspose.Words का उपयोग करके अपनी तालिका के लिए एक कस्टम शैली बना ली है।

### .NET के लिए Aspose.Words का उपयोग करके टेबल स्टाइल बनाने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके टेबल स्टाइल कैसे बनाया जाता है। इस चरण-दर-चरण गाइड का पालन करके, आप अपने Word दस्तावेज़ों में अपनी टेबल की शैली को आसानी से अनुकूलित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में टेबल को मैनिपुलेट करने और फ़ॉर्मेट करने के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति को बेहतर बना सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।