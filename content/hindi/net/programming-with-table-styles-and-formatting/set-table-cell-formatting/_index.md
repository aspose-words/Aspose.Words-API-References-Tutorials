---
title: तालिका सेल स्वरूपण सेट करें
linktitle: तालिका सेल स्वरूपण सेट करें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके तालिका कक्ष स्वरूपण सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके टेबल सेल के फ़ॉर्मेटिंग को परिभाषित करने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को अपने प्रोजेक्ट में समझने और लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों की तालिकाओं में सेल की चौड़ाई और मार्जिन (पैडिंग) को कैसे समायोजित किया जाए।

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
builder. StartTable();
builder. InsertCell();
```

## चरण 4: सेल फ़ॉर्मेटिंग सेट करें
 अब हम सेल फ़ॉर्मेटिंग को एक्सेस करके सेट कर सकते हैं`CellFormat` वस्तु का`DocumentBuilder` ऑब्जेक्ट। हम संबंधित गुणों का उपयोग करके सेल की चौड़ाई और मार्जिन (पैडिंग) सेट कर सकते हैं।

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## चरण 5: सेल में सामग्री जोड़ें
 फिर हम दस्तावेज़ बिल्डर का उपयोग करके सेल में सामग्री जोड़ सकते हैं`Writeln()` तरीका।

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## चरण 6: तालिका समाप्त करें और दस्तावेज़ सहेजें
 अंत में, हम तालिका का निर्माण पूरा करते हैं`EndRow()` विधि और`EndTable()`, फिर हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं।

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके टेबल सेल फ़ॉर्मेटिंग सेट करने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके टेबल सेल की फ़ॉर्मेटिंग कैसे सेट करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में अपनी तालिकाओं में सेल की चौड़ाई और मार्जिन को आसानी से समायोजित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपनी तालिकाओं के विज़ुअल लेआउट को अपनी विशिष्ट आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।