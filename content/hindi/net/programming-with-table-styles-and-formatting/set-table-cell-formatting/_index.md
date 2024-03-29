---
title: टेबल सेल फ़ॉर्मेटिंग सेट करें
linktitle: टेबल सेल फ़ॉर्मेटिंग सेट करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके तालिका सेल फ़ॉर्मेटिंग सेट करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके तालिका सेल के स्वरूपण को परिभाषित करने के लिए चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों की तालिकाओं में सेल की चौड़ाई और मार्जिन (पैडिंग) को कैसे समायोजित करें।

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
builder. StartTable();
builder. InsertCell();
```

## चरण 4: सेल फ़ॉर्मेटिंग सेट करें
 अब हम एक्सेस करके सेल फ़ॉर्मेटिंग सेट कर सकते हैं`CellFormat` की वस्तु`DocumentBuilder` वस्तु। हम संबंधित गुणों का उपयोग करके सेल की चौड़ाई और मार्जिन (पैडिंग) सेट कर सकते हैं।

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
 अंत में, हम इसका उपयोग करके तालिका बनाना समाप्त करते हैं`EndRow()` विधि और`EndTable()`, फिर हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं।

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सेट टेबल सेल फ़ॉर्मेटिंग के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके टेबल सेल की फ़ॉर्मेटिंग कैसे सेट करें। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में अपनी तालिकाओं में सेल की चौड़ाई और मार्जिन को आसानी से समायोजित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान के साथ, आप अपनी तालिकाओं के विज़ुअल लेआउट को अपनी विशिष्ट आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।