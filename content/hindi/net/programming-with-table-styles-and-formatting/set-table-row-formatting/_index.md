---
title: तालिका पंक्ति स्वरूपण सेट करें
linktitle: तालिका पंक्ति स्वरूपण सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति स्वरूपण सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके टेबल रो फ़ॉर्मेटिंग सेट करने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको अपने प्रोजेक्ट में इस सुविधा को समझने और लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में टेबल रो की ऊँचाई और पैडिंग को कैसे समायोजित किया जाए।

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

## चरण 3: एक नई तालिका शुरू करें और एक सेल जोड़ें
तालिका बनाना शुरू करने के लिए, हम उपयोग करते हैं`StartTable()` दस्तावेज़ निर्माता की विधि, फिर हम तालिका में एक सेल जोड़ते हैं`InsertCell()` तरीका।

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## चरण 4: लाइन फ़ॉर्मेटिंग परिभाषित करें
 अब हम तक पहुँच कर पंक्ति स्वरूपण सेट कर सकते हैं`RowFormat` वस्तु का`DocumentBuilder` ऑब्जेक्ट। हम संबंधित गुणों का उपयोग करके लाइन की ऊंचाई और मार्जिन (पैडिंग) सेट कर सकते हैं।

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## चरण 5: तालिका मार्जिन सेट करें
 इसके बाद, हम तालिका के संगत गुणों तक पहुँच कर तालिका पैडिंग सेट कर सकते हैं`Table` ये मार्जिन तालिका की सभी पंक्तियों पर लागू होंगे।

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

 अंत में, हम तालिका का निर्माण समाप्त करते हैं`EndRow()` और`EndTable()` विधि, फिर हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं।

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके तालिका पंक्ति स्वरूपण सेट करने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// ये स्वरूपण गुण तालिका पर सेट किए जाते हैं और तालिका की सभी पंक्तियों पर लागू होते हैं।
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके टेबल रो फ़ॉर्मेटिंग कैसे सेट करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में टेबल रो की ऊँचाई और मार्जिन को आसानी से समायोजित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में टेबल को मैनिपुलेट करने और फ़ॉर्मेट करने के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपनी टेबल के विज़ुअल लेआउट को अपनी विशिष्ट आवश्यकताओं के अनुसार कस्टमाइज़ कर सकते हैं।