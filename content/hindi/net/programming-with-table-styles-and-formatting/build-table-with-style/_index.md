---
title: स्टाइल के साथ टेबल बनाएं
linktitle: स्टाइल के साथ टेबल बनाएं
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके कस्टम शैली के साथ तालिका बनाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Words का उपयोग करके एक स्टाइल तालिका बनाने की चरण-दर-चरण प्रक्रिया के बारे में बताएंगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को समझने और अपनी परियोजनाओं में लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि .NET के लिए Aspose.Words का उपयोग करके अपने Word दस्तावेज़ों में कस्टम शैली के साथ एक तालिका कैसे बनाएं।

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

## चरण 3: एक नई तालिका प्रारंभ करें और एक सेल डालें
 तालिका का निर्माण शुरू करने के लिए, हम इसका उपयोग करते हैं`StartTable()` दस्तावेज़ निर्माता की विधि, फिर हम इसका उपयोग करके तालिका में एक सेल सम्मिलित करते हैं`InsertCell()` तरीका।

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## चरण 4: तालिका की शैली परिभाषित करें
 अब हम इसका उपयोग करके तालिका शैली सेट कर सकते हैं`StyleIdentifier` संपत्ति। इस उदाहरण में, हम "MediumShading1Accent1" शैली का उपयोग कर रहे हैं।

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## चरण 5: तालिका में शैली विकल्प लागू करें
 हम निर्दिष्ट कर सकते हैं कि शैली का उपयोग करके किन विशेषताओं को स्वरूपित किया जाना चाहिए`StyleOptions`सरणी की संपत्ति. इस उदाहरण में, हम निम्नलिखित विकल्प लागू करते हैं: "फर्स्टकॉलम", "रोबैंड्स" और "फर्स्टरो"।

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## चरण 6: तालिका का आकार स्वचालित रूप से समायोजित करें
 इसकी सामग्री के आधार पर सरणी के आकार को स्वचालित रूप से समायोजित करने के लिए, हम इसका उपयोग करते हैं`AutoFit()` विधि के साथ`AutoFitBehavior.AutoFitToContents` व्यवहार।

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## चरण 7: कक्षों में सामग्री जोड़ें
 अब हम इसका उपयोग करके कोशिकाओं में सामग्री जोड़ सकते हैं`Writeln()` और`InsertCell()` दस्तावेज़ निर्माता की विधियाँ. इस उदाहरण में, हम "आइटम" और "मात्रा (

किग्रा)" और संबंधित डेटा।

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## चरण 8: संशोधित दस्तावेज़ सहेजें
अंत में, हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं। आप आउटपुट दस्तावेज़ के लिए उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

बधाई हो! अब आपने .NET के लिए Aspose.Words का उपयोग करके एक कस्टम स्टाइल तालिका बनाई है।

### .NET के लिए Aspose.Words का उपयोग करके स्टाइल के साथ तालिका बनाने के लिए नमूना स्रोत कोड 

```csharp
	// आपकी दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// हमें किसी भी तालिका फ़ॉर्मेटिंग को सेट करने से पहले कम से कम एक पंक्ति सम्मिलित करनी होगी।
	builder.InsertCell();
	// अद्वितीय शैली पहचानकर्ता के आधार पर प्रयुक्त तालिका शैली सेट करें।
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// लागू करें कि किन विशेषताओं को शैली के अनुसार स्वरूपित किया जाना चाहिए।
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके एक स्टाइल तालिका कैसे बनाई जाए। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने Word दस्तावेज़ों में अपनी तालिकाओं की शैली को आसानी से अनुकूलित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में तालिकाओं में हेरफेर और फ़ॉर्मेटिंग के लिए एक शक्तिशाली और लचीली API प्रदान करता है। इस ज्ञान से, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति में सुधार कर सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।