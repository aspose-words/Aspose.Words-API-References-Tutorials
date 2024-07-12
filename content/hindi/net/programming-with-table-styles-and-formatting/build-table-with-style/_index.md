---
title: स्टाइल के साथ टेबल बनाएं
linktitle: स्टाइल के साथ टेबल बनाएं
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके कस्टम शैली के साथ तालिका बनाने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

इस ट्यूटोरियल में, हम आपको Aspose.Words for .NET का उपयोग करके स्टाइल वाली टेबल बनाने की चरण-दर-चरण प्रक्रिया से अवगत कराएँगे। हम बंडल किए गए C# स्रोत कोड की व्याख्या करेंगे और आपको इस सुविधा को अपने स्वयं के प्रोजेक्ट में समझने और लागू करने में मदद करने के लिए एक व्यापक मार्गदर्शिका प्रदान करेंगे। इस ट्यूटोरियल के अंत में, आप जानेंगे कि Aspose.Words for .NET का उपयोग करके अपने Word दस्तावेज़ों में कस्टम स्टाइल वाली टेबल कैसे बनाएँ।

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

## चरण 3: एक नई तालिका शुरू करें और एक सेल डालें
 तालिका का निर्माण शुरू करने के लिए, हम उपयोग करते हैं`StartTable()` दस्तावेज़ बिल्डर की विधि, फिर हम तालिका में एक सेल का उपयोग करके सम्मिलित करते हैं`InsertCell()` तरीका।

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## चरण 4: तालिका की शैली निर्धारित करें
 अब हम इसका उपयोग करके तालिका शैली सेट कर सकते हैं`StyleIdentifier` इस उदाहरण में, हम "MediumShading1Accent1" शैली का उपयोग कर रहे हैं।

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## चरण 5: तालिका पर शैली विकल्प लागू करें
 हम यह निर्दिष्ट कर सकते हैं कि कौन सी विशेषताओं को शैली द्वारा प्रारूपित किया जाना चाहिए`StyleOptions`सरणी की संपत्ति। इस उदाहरण में, हम निम्नलिखित विकल्प लागू करते हैं: "FirstColumn", "RowBands" और "FirstRow"।

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## चरण 6: तालिका आकार को स्वचालित रूप से समायोजित करें
 सारणी के आकार को उसकी सामग्री के आधार पर स्वचालित रूप से समायोजित करने के लिए, हम इसका उपयोग करते हैं`AutoFit()` विधि के साथ`AutoFitBehavior.AutoFitToContents` व्यवहार।

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## चरण 7: कक्षों में सामग्री जोड़ें
 अब हम इसका उपयोग करके कोशिकाओं में सामग्री जोड़ सकते हैं`Writeln()`और`InsertCell()` दस्तावेज़ बिल्डर के तरीके। इस उदाहरण में, हम "आइटम" और "मात्रा (

किलोग्राम)" और संबंधित डेटा।

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

## चरण 8: संशोधित दस्तावेज़ को सहेजें
अंत में, हम संशोधित दस्तावेज़ को एक फ़ाइल में सहेजते हैं। आप आउटपुट दस्तावेज़ के लिए एक उपयुक्त नाम और स्थान चुन सकते हैं।

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

बधाई हो! आपने अब .NET के लिए Aspose.Words का उपयोग करके एक कस्टम स्टाइल वाली तालिका बना ली है।

### .NET के लिए Aspose.Words का उपयोग करके स्टाइल के साथ तालिका बनाने के लिए नमूना स्रोत कोड 

```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// किसी भी तालिका स्वरूपण को सेट करने से पहले हमें कम से कम एक पंक्ति अवश्य सम्मिलित करनी चाहिए।
	builder.InsertCell();
	// अद्वितीय शैली पहचानकर्ता के आधार पर प्रयुक्त तालिका शैली सेट करें।
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// कौन सी सुविधाओं को शैली के अनुसार प्रारूपित किया जाना चाहिए, इसे लागू करें.
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
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Words का उपयोग करके स्टाइल वाली टेबल कैसे बनाई जाती है। इस चरण-दर-चरण गाइड का पालन करके, आप अपने Word दस्तावेज़ों में अपनी टेबल की शैली को आसानी से अनुकूलित कर सकते हैं। Aspose.Words आपके दस्तावेज़ों में टेबल को मैनिपुलेट करने और फ़ॉर्मेट करने के लिए एक शक्तिशाली और लचीला API प्रदान करता है। इस ज्ञान के साथ, आप अपने Word दस्तावेज़ों की दृश्य प्रस्तुति को बेहतर बना सकते हैं और विशिष्ट आवश्यकताओं को पूरा कर सकते हैं।