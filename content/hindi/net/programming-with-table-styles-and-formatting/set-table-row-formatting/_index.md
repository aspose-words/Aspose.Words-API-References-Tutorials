---
title: तालिका पंक्ति स्वरूपण सेट करें
linktitle: तालिका पंक्ति स्वरूपण सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति फ़ॉर्मेटिंग सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति फ़ॉर्मेटिंग सेट करने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में तालिका पंक्ति की ऊंचाई और पैडिंग को कैसे समायोजित करें।

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

## चरण 3: एक नई तालिका प्रारंभ करें और एक सेल जोड़ें
तालिका बनाना शुरू करने के लिए, हम इसका उपयोग करते हैं`StartTable()` दस्तावेज़ कंस्ट्रक्टर की विधि, फिर हम इसका उपयोग करके तालिका में एक सेल जोड़ते हैं`InsertCell()` तरीका।

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## चरण 4: लाइन फ़ॉर्मेटिंग को परिभाषित करें
 अब हम एक्सेस करके पंक्ति फ़ॉर्मेटिंग सेट कर सकते हैं`RowFormat` की वस्तु`DocumentBuilder` वस्तु। हम संबंधित गुणों का उपयोग करके लाइन की ऊंचाई और मार्जिन (पैडिंग) सेट कर सकते हैं।

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## चरण 5: तालिका मार्जिन सेट करें
 इसके बाद, हम संबंधित गुणों तक पहुंच कर तालिका पैडिंग सेट कर सकते हैं`Table` वस्तु। ये मार्जिन तालिका की सभी पंक्तियों पर लागू होंगे।

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## चरण 6: पंक्ति में सामग्री जोड़ें
 अंत में, हम दस्तावेज़ बिल्डर का उपयोग करके लाइन में सामग्री जोड़ सकते हैं`Writeln()` तरीका।

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## चरण 7: तालिका समाप्त करें और दस्तावेज़ सहेजें
में

 अंत में, हम इसका उपयोग करके तालिका बनाना समाप्त करते हैं`EndRow()` और`EndTable()` विधि, फिर हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं।

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सेट टेबल पंक्ति फ़ॉर्मेटिंग के लिए नमूना स्रोत कोड 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके टेबल पंक्ति फ़ॉर्मेटिंग कैसे सेट करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में तालिका पंक्ति की ऊंचाई और मार्जिन को आसानी से समायोजित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान के साथ, आप अपनी तालिकाओं के विज़ुअल लेआउट को अपनी विशिष्ट आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।